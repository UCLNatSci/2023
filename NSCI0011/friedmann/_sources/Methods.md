# Friedmann Equation Methods

Solving the Friedmann equations is in general *hard* because the equation contains a non-linear ODE term.  However by simplifying the system a little (and tracking your assumptions), finding some solutions with analytical methods is straightforward.

A firs assumption is to make the pressure $P$ here zero, $P= 0$, this simplifies the system to:

```{math}
\dot{\rho} = -3 \frac{\dot{a}}{a}\rho
```

this is a separable ODE:
```{math}
\int \frac{\mathrm{d}\rho}{\rho} = -3 \int \frac{\mathrm{d}a}{a} \Rightarrow \rho = C a^{-3} 
```

which we can then use to solve the Friedmann equations.  Lets further assume that $k = \Lambda = 0$ and $8 \pi G  = c = 1$:
```{math}
\left(\frac{\dot{a}}{a}\right)^2 = \frac{a^{-3}}{3} \Rightarrow a = C t^{2/3}
```

we can further look at other examples of pressure relations, for radiation $P = \frac{1}{3}\rho$.  This corresponds to a universe dominated with radiation, rather than matter.  

If we solve this system, we find $a = C t^{1/2}$ (try this yourself).

We can make a more general relation, $P = w \rho$ where $w$ is known as the equation of state paramater and in the first instance is a constant.

Find the most general solution to the Friedmann equations for no curvative, cosmological constant and constant $w$