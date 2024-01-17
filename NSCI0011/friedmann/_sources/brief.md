# Looking at Numerical Solutions

We can think further about solutions to the Friedmann equations by using an ODE solver, however since these equations are non-linear in the first instance we have to be careful about how we write them in order to do this.

We can look at a code that solves a simple harmonic system for a mass on a spring, $m \ddot{x} + k x = 0$:

```	python
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

As we see this solves the system and produces an output for $x(t)$ and also $v(t) = \dot{x}(t)$.

```{figure} ./figures/run1.png
---
name: run1
---
```

How did we get this into the form that python can then solve it?

Firstly 