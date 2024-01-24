# Looking at Numerical Solutions to ODEs

## Using odeint

We can think further about solutions to the Friedmann equations by using an ODE solver, however since these equations are non-linear in the first instance we have to be careful about how we write them in order to do this.

We can look at a code that solves a simple harmonic system for a mass on a spring, $m \ddot{x} + k x = 0$:

````{admonition} ODE code using odeint
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
m = 1.0  # Mass
k = 10.0  # Spring constant

# Time span
t_span = np.linspace(0, 10, 1000)

# Solve the ODE using odeint
solution = odeint(
    shm_system,
    initial_conditions,
    t_span,
    args=(m, k)
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

## Using solve_ivp

It turns out that python has *other* ODE packages - `odeint` is problably the most widespread one, but it only has one sort of solver, but there is a more versatile package - `solve_ivp`.

````{admonition} ODE code in solve_ivp
:class: dropdown
```python
import numpy as np
from scipy.integrate import solve_ivp
import matplotlib.pyplot as plt

# Define the differential equation for the mass-spring system
def mass_spring_system(t, y, k, m):
    x, v = y
    dxdt = v
    dvdt = -k / m * x
    return [dxdt, dvdt]

# Set up initial conditions and parameters
initial_conditions = [1.0, 0.0]  # Initial displacement and velocity
m = 1.0  # Mass
k = 10.0  # Spring constant


# Set up time range
t_span = (0, 10)

# Solve the differential equation using solve_ivp
solution = solve_ivp(
    mass_spring_system, 
    t_span, 
    initial_conditions, 
    args=(k, m), 
    dense_output=True)

# Evaluate the solution at specific time points
t_eval = np.linspace(0, 10, 1000)
y_eval = solution.sol(t_eval)

# Extract displacement and velocity from the solution
x, v = y_eval

# Plot the results
plt.figure(figsize=(10, 4))
plt.plot(t_eval, x, label='Displacement (x)')
plt.plot(t_eval, v, label='Velocity (v)')
plt.xlabel('Time')
plt.ylabel('Amplitude')
plt.legend()
plt.title('Simple Harmonic Motion (SHM) System')
plt.grid(True)
plt.show()
```
````
## Exercises 

````{admonition} Exercises with ODE solvers

1\. Write a code to solve a damped harmonic oscillator:
```{math}
\ddot{x} + 2 \omega_0 \zeta \dot{x} + \omega_0^2 x = 0
```
where $\omega_0^2 = k/m$ and the damping ratio $\zeta$ can take different values.  

2\. Plot solutions for $\zeta = 0,\, \zeta = 0.5, \zeta = 1, \zeta = 2$ and pick sensible values of other parameters, plotting a time series $x(t)$ vs $t$.

Also try plotting a phase portrait here - i.e. $x(t)$ vs $\dot{x}(t)$.

3\. Add a source term to the ODE:
```{math}
\ddot{x} + 2 \omega_0 \zeta \dot{x} + \omega_0^2 x = F_0\,\cos(\Omega t)
```
where we can add in an oscilating term with amplitude $F_0$ and frequency $\Omega$.


````

