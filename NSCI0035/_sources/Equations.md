# The Friedmann Equations

## General Relativity
Relativistic cosmology is the study of the beginnings, expansion and inevitable
fate of the entire universe.  The equations of Einstein's theory of general relativity are complicated:

```{math}
R_{\mu\,\nu} - \frac{1}{2}R\,g_{\mu\,\nu} = \frac{8 \pi G}{c^4}T_{\mu\,\nu}
```

We can simplify by constructing a universe that expands in a way that is homogeneous and isotropic (something we observe on large scales), we do this using the Friedman Lemaitre Robertson Walker (FLRW) metric, which we can write as:
```{math}
\mathrm{d}s^2 = g_{\mu\,\nu}\, \mathrm{d}x^{\mu}\,\mathrm{d}x^\nu = -c^2\mathrm{d}t^2 + a(t) \left[ \frac{\mathrm{d}r^2}{1-kr^2} + r^2\left( \mathrm{d}\theta^2 + \sin^2(\phi)^2\,\mathrm{d}\phi^2\right)\right]
```
and by assuming a *perfect fluid* form of the stress-energy tensor:
```{math}
T_{\mu\,\nu} = \begin{pmatrix} -\rho\,c^2 & & & \\ & P & & \\ & & P & \\ & & & P \end{pmatrix}
```
we find the equations of matter and energy reduce down to the Friedmann equations.

## The three Friedmann equations
```{math}
H^2 = \left(\frac{\dot{a}}{a}\right)^2 &= \frac{8 \pi G}{3} \rho - \frac{kc^2}{a^2} + \frac{\Lambda c^2}{3} \\ 
\frac{\ddot{a}}{a} &= - \frac{4 \pi G}{3}\left(\rho + \frac{3P}{c^2}\right) + \frac{\Lambda c^2}{3} \\ 
\dot{\rho} &= -3\frac{\dot{a}}{a} \left(\rho + \frac{P}{c^2}\right)
```

where $a(t)$ is the scaling factor space, $\rho$ is the matter/energy density, $P$ is the pressure, $k$ is the curvature parameter, $c$ is the speed of light and $\Lambda$ is the cosmological constant.  

The first equation is often called the *energy equation* (F1), the second equation is often called the *acceleration equation* (F2) and the final equation the *conservation equation* (F3).  These equations are not three independent equations however, if we take F1, rearrange and differentiate with respect to time:

```{math}
\dot{a}^2 &= \frac{8 \pi G}{3}\rho a^2 - \frac{kc^2}{a^2} + \frac{\Lambda c^2}{3}a^2 \\
2 \ddot{a}\dot{a} &= \frac{8 \pi G}{3}\left(\dot{\rho} a^2 + 2 \dot{a}a\rho\right) + 2 \dot{a} a \frac{\Lambda c^2}{3} \\
```
then using F3 we can find:
```{math}
\frac{\dot{\rho}a}{2\dot{a}} &= -\frac{3}{2}\left(\rho + \frac{P}{c^2}\right) \\
\frac{\ddot{a}}{a} &= -\frac{4\pi G}{3}\left(\rho + \frac{P}{c^2}\right) + \frac{\Lambda c^2}{3}
```
which is exactly the form of F2.

## Curvature 

The curvature of the universe is important in solving these equations, we find the the parameter $k$ is related to this.  We can see graphically that the different cases of $k$:

```{figure} ./figures/curvature.png
---
name: curvature
---
```
When the curvature is positive, $k > 0$ and this represents spaces that look like a ball and can only represent a finite sized universe.  When the curvature is zero, $k=0$, the space is flat, which can represent either a finite or an infinite universe.  When the curvature is negative, $k < 0$, the space is saddle shaped and can represent either a finite or infinite universe.

## Cosmological Constant

The term $\Lambda$ in these equations represents a cosmological constant.  This was a term first added to the Einstein equations by Einstein himself when it was realised that without it the solutions for a universe would not be static (this represented the current thinking at the time).  When Edwin Hubble made observations that produced his celebrated Hubbles law $v = H d$, which suggests that more distant galaxies have more red-shifted light (and therefore are moving faster) than closer galaxies, Einstein removed this term and famously called it the greatest blunder in his career.  From about 1990 onwards, observations of so-called standard candle type 1A super novae (that are thought to always produce light of roughly the same luminsity) suggested that the light from distant galaxies was not just affected by the expansion of the universe, but that this expansion was **accelerating**!  This would require a significant additional effect within the friedmann equations, which we model through the term $\Lambda$.

We believe that the universe underwent many different regimes of scaling behaviour in the scale factor:
```{figure} ./figures/domination_regimes.png
---
name: domination_regimes
---
The panels left to right shows the effect of radiation domiation, then matter domination and finally $\Lambda$ domination.
```