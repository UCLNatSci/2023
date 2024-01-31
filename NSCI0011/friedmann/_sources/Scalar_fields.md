# Looking at scalar fields

## Scalar field basics

We can imagine a source of energy in the universe sourced by a scalar field $\phi$.  If we imagine that the universe is homogenous and isotropic, then the field is just a function of time, so $\phi=\phi(t)$.

We can find the energy density $\rho(t)$ and effective pressure $P(t)$ associated with this scalar field $\phi(t)$, so this provides a useful way to source energy and matter content of the universe.  Astronomers believe that if this field is detected, it could be responsible for both large scale and small scale growth of structure in the universe as well as potentially dark energy.

We find the the energy density and pressure are given by:

```{math}
\rho &= \frac{1}{2}\dot{\phi}^2 + V(\phi) \\
P &= \frac{1}{2}\dot{\phi}^2 - V(\phi)
```

which we can interpret as the kinetic energy $\frac{1}{2}\dot{\phi}^2$ and the potential energy $V(\phi)$ either added (the Hamiltonian density) or subtracted (the Lagrangian density).

## Friedmann universe with scalar fields

These can then be inserted into the Friedmann equations, which we can write after some algebra as:
```{math}
\ddot{\phi} + 3H \dot{\phi} + \frac{\partial V}{\partial \phi} &= 0 \\
\dot{\phi}^2 - 6H^2 + 2V &= 0
```
where $H = \dot{a} / a$, so clearly we can use these as a different way to look at dynamial systems.



````{admonition} Exercises for week 4
1\. Fill in the gaps for the derivation of the scalar field equations of motion above - can you derive these too?

2\. Think about how to input the scalar field equations into Python's ODE solver - recall we need coupled 1st order ODEs.

3\. Make the first choice for the potential energy $V(\phi) = \frac{1}{2}m\phi^2$ and try to find some solutions for $\phi(t)$ and therefore for $a(t)$.

4\. Use a phase portrait method to see if there are any interesting solutions - it is possible to get **inflationary** solutions using this - look up slow roll inflation in the references. 
````
