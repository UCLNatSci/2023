# The Friedmann Equations


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