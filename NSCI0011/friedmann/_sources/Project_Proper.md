# Getting started on the project

## Recap

We have used a variey of methods, including dynamical systems ideas, to try and solve some simplified (and the more increasingly complicated) Friedmann equations.

Now you need to decide which methods you will employ to find solutions to the equations and hence find different univdrse behaviours.

## Equations of Motion

We can think about a few different tracks in which to solve this system of equations, for the Friedmann equations theselves, employing an equation of state, we find these can combined together and written as a second order ODE:
```{math}
\ddot{a} = -\frac{1+3w}{2a}\left( \dot{a}^2 + k\right) + \frac{1}{2}a\Lambda (1+w)
```

Likewise given the scalar field follows:
```{math}
\ddot{\phi} + 3 H\dot{\phi} + + \frac{\partial V}{\partial \phi} &= 0 \\
 \dot{\phi}^2 - 6H^2  + 2V &= 0
```

We can use this to find solutions of $\phi$ based on values of $H$ and then solve this system to find $a(t)$.

````{admonition} Tasks for Weeks 5-10

1\. Make sure that we have completed all of the exercises from weeks 2-4, the codes and equations you find are *useful*!

2\. Pick an approach - the friedmann system or the scalar field system, start making assumptions about different values and getting solutions out.

3\. Choose a paramter space to explore - e.g. if we vary $w$ or $k$ or $\Lambda$, what is the effect on $a(t)$.  A systematic exploration of these sorts of parameters is a good outcome for this project!

````