# Introduction

The Friedmann equations are a set of equations in *physical* cosmology that govern the expansion of space in homogeneous and isotropic models of the universe within the context of general relativity. 

They were first derived by Alexander Friedmann in 1922 from Einstein's field equations of gravitation for the Friedmann–Lemaître–Robertson–Walker metric and a perfect fluid with a given mass density $\rho$ and pressure $P$. 

The Friedmann equations form the basis of the $\Lambda$CDM model, which posits that the universe is filled with:

```{figure} ./figures/makeup.jpeg
---
name: makeup
---
The makeup of the energy-matter content of the universe, as found from the Planck satellite data.
```

Solving these equations can pose some analytial (and numerical) difficulties, because of the non-linear term in the first equation and the fact that there are several functions - although these are at least just ODE's in time.

In this project we will look at different approaches taken to solving this system, both analytical and numerical.