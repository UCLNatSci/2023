# Friedmann Equation Methods

## First Go

Solving the Friedmann equations is in general *hard* because the equation contains a non-linear ODE term.  However by simplifying the system a little (and tracking your assumptions), finding some solutions with analytical methods is straightforward.

A first assumption is to make the pressure $P$ here zero, $P= 0$, this simplifies the third equation to:

```{math}
\dot{\rho} = -3 \frac{\dot{a}}{a}\rho
```

this is a separable ODE:
```{math}
\int \frac{\mathrm{d}\rho}{\rho} = -3 \int \frac{\mathrm{d}a}{a} \Rightarrow \rho = C a^{-3} 
```

which we can then use to solve the Friedmann equations.  

Lets further assume that $k = \Lambda = 0$ and $8 \pi G  = c = 1$ - we call this assumption using *natural units*, it helps us to get solutions to the problems without worrying about scales.

Hence we can find a seperable solution to the ODEs as we can substitute in $\rho(a)$ into the first equation and then solve it.

```{math}
\left(\frac{\dot{a}}{a}\right)^2 = \frac{a^{-3}}{3} \Rightarrow a = C t^{2/3}
```
Note that we used $a(t=0) = 0$ here - this is actually the Big Bang in this models.

we can further look at other examples of pressure relations, for radiation $P = \frac{1}{3}\rho$.  This corresponds to a universe dominated with radiation, rather than matter.  

If we solve this system, we find $a = C t^{1/2}$ (try this yourself).

## Equation of State 
We can make a more general relation, $P = w \rho$ where $w$ is known as the equation of state paramater and in the first instance is a constant.

We can the most general solution to the Friedmann equations for no curvative, no cosmological constant and a constant $w$, it looks like:

```{math}
a \sim t^{2/3(1+w)}
```

which is a valid solution for every value of $w$, except $w=-1$.

## Cosmological Constant Domination

What about if our cosmological constant is large (we expect at this point in the current universes history it is!), how does this change our solutions?

Solve the equation given by:
```{math}
\left( \frac{\dot{a}}{a}\right)^2 \simeq \frac{\Lambda}{3}
```

which hopefully we can see has an expontential solution:

```{math}
a = a_0 e^{\sqrt{\Lambda/3} t}
```

which obviously means an exponetially growing universe - we call this phase $\Lambda$ or dark energy domination.

It is thought the $w = -1$ produces the same form of solutions - is this true? (think about where you would divide by zero in your $w$ solutions).

```{admonition} Exercise for week 2

Solve the Friedmann equations for $P = w \rho$, $\Lambda = 0$ and $k \neq 0$ - how do the solutions now change for the radiation dominated case?

You will need to submit these pen and paper solutions, so write something neatly!
```