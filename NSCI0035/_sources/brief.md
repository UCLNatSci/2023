# Looking at Numerical Solutions

We can think further about solutions to the Friedmann equations by using an ODE solver, however since these equations are non-linear in the first instance we have to be careful about how we write them in order to do this.

We can look at a code that solves a simple harmonic system for a mass on a spring, $m \ddot{x} + k x = 0$:

````{admonition} ODE code
:class: dropdown

```python
import numpy as np
from scipy.integrate import odeint
import matplotlib.pyplot as plt

# Simple Harmonic Motion (SHM) system ODE
def shm_system(y, t, m, k):
    x, v = y
    dxdt = v
    dvdt = -(k/m) * x
    return [dxdt, dvdt]

# Initial conditions
initial_conditions = [1.0, 0.0]  # initial displacement and velocity

# Parameters
mass = 1.0
spring_constant = 10.0

# Time span
t_span = np.linspace(0, 10, 1000)

# Solve the ODE using odeint
solution = odeint(
    shm_system,
    initial_conditions,
    t_span,
    args=(mass, spring_constant)
)

# Extract displacement and velocity from the solution
displacement, velocity = solution.T

# Plot the results
plt.figure(figsize=(10, 4))
plt.plot(t_span, displacement, label='Displacement (x)')
plt.plot(t_span, velocity, label='Velocity (v)')
plt.xlabel('Time')
plt.ylabel('Amplitude')
plt.legend()
plt.title('Simple Harmonic Motion (SHM) System')
plt.grid(True)
plt.show()
```
````

As we see this solves the system and produces an output for $x(t)$ and also $v(t) = \dot{x}(t)$.

```{figure} ./figures/run1.png
---
name: run1
---
```

How did we get this into the form that python can then solve it?

Firstly lets look at what `odeint` requires, we need the equations in the form of a coupled system of first order equations (rather than as a second order system), so we can turn
```{math}
m\ddot{x} + k x = 0 \Rightarrow \ddot{x} + \frac{k}{m}x = 0
```

into a new system, where we define the velocity intermediate variable $v = \dot{x}$ and so rewrite as:
```{math}
\dot{x} &= v \\
\dot{v} &= -\frac{k}{m} x
```

which we can recognise as the two lines in the function `shm_system`.
```python 
# Simple Harmonic Motion (SHM) system ODE
def shm_system(y, t, m, k):
    x, v = y
    dxdt = v
    dvdt = -(k/m) * x
    return [dxdt, dvdt]
```

We also need to put in some initial conditions - as we are solving a second order system, we need two of these and they're represent $x(t=0)$ and $\dot{x}(t=0)$.  
```python
initial_conditions = [1.0, 0.0] 
```

We set up a range of $t$ values for the solution in the `t_span` which is an array of 1000 linearly spaced points from $0 \leq t \leq 10$.
```python
t_span = np.linspace(0, 10, 1000)
```

We also pass the paramters `mass` and `spring_constant` to `odeint`, 
```python
solution = odeint(
    shm_system,
    initial_conditions,
    t_span,
    args=(mass, spring_constant)
)
```

The output is an array which we transpose and the first column here is $x(t)$ and the second $\dot{x}(t)$, which will be the same length as `t_span`, 

```python
displacement, velocity = solution.T
```

and finally we plot the results.