# Friedmann Equations Numerical Methods

Before we can put our system of equations into Python, we should look at ways to rewrite them.

For the simplest solutions, with $k = \lambda = 0$, using equation of state $P = w \rho$ and in the units of $8 \pi G = c = 1$, so we can try:
```{math}
\dot{a}^2 &= \frac{\rho\,a^2}{3} \\
\ddot{a} &= -\frac{\rho \,a}{6} (1+3w) \\
\dot{\rho} &= -3\frac{\dot{a}}{a}\rho\,(1+w)
```

If we use the third equation, then we can find:
```{math}
\int \frac{\mathrm{d} \rho}{\rho} = -3\int \frac{(1+w)}{a}\,\mathrm{d}a
```

We could integrate this up as usual and insert an integration constant, but an easier way to use equations here is to write the solutions in a dimension-less form:

```{math}
\frac{\rho}{\rho_0} = \left(\frac{a}{a_0} \right)^{-3(1+w)}
```

where $\rho_0$ and $a_0$ are some initial values of $\rho$ and $a$ respectively.

If we insert this into equation 1, it will turn into:
```{math}
\dot{a} = \left( \frac{\rho_0\,a_0^{3(1+w)}}{3}\right)^{1/2}a^{-(1+3w)/2}
```

So integrating this up, we find:
```{math}
\int a^{(1+3w)/2}\,\mathrm{d}a &= \int \left(\dots \right)\,\mathrm{d}t \\
\Rightarrow \left(\frac{a}{a_0}\right)^{3(1+w)/2}&= \frac{t}{t_0} \\
\frac{a}{a_0} &= \left(\frac{t}{t_0} \right)^{2/3(1+w)}
```

This sort of form is most useful for numerically solving the system, because it allows us to integrate over a range $t \in [t_i,\, t_f]$.

````{admonition} Exercises for week 3

1\. In our system, the ODE equations look like:
```{math}
\dot{a} &= \sqrt{\frac{\rho}{3}}a \\
\dot{\rho} &= -3\frac{\dot{a}}{a}\rho\,(1+w)
```

Input these into a Python code and solve for the values of $w = 0,\, \frac{1}{3}$ - check these against the analytical solutions.  Plot $a(t)$ vs $t$ and aso $\rho(t)$ vs $t$.  

2\. Start making the system more complicated - try $k = -1$ and $\Lambda > 0$.

(extra) Try getting a phase portrait - either $a$ vs $\dot{a}$ and/or $\rho$ vs $\dot{\rho}$.

3\. Look through the different approaches for solving these systems in the project brief - think about the equations that you will need to solve in each case and which approach you would like to explore.  (Hint, some are first order ODEs, some are second order ODEs).

````