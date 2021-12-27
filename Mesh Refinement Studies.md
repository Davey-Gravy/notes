# Mesh Refinement Studies

An ideal CFD mesh has an infinite number of cells, which is not practical
- a finite number of cells must be used --> discretization error
	- linear interpolation of profiles
- mesh refinement study can estimate discretization error
	- run CFD model for meshes of varying size
	- tool for choosing the optimal mesh that balances
		- accuracy
		- computational expense

## Discretization Error

Consider a general flow quantity $\phi$. Over a small distance, the profile of $\phi$ can be represented by a Taylor series expansion:

$$
\phi = c_0 + c_1x+c_2x^2+c_3x^3 + \dots +c_nx^n
$$

CFD codes use linear variation between cells:

$$
\phi_\text{CFD} = c_0+c_1x
$$

Discretization error is given by the difference between the Taylor series representation and the CFD approximation:

$$
e = \phi - \phi_\text{CFD}=c_2+c_3x^3+\dots+c_nx^n
$$

The error is proportional to distance squared ($x^2$)
- reducing distance by 1/2 reduces error by 1/4
	- second-order accurate, $p=2$

In reality, upwind schemes and gradient limiters make CFD codes a bit less than second-order accurate

Often think of mesh refinement as number of cells
Should be though of in terms of cell size --> representative cell length $h$

$$
h = \frac{1}{N}\sum_\text{cells}V_p^{1/3}
$$

### Mesh Density

Representative cell length should differ by at least 30% between each mesh

$$
r = \frac{h_\text{coarse}}{h_\text{medium}} > 1.3\qquad r= \frac{h_\text{medium}}{h_\text{fine}} > 1.3
$$

## Richardson Extrapolation

Having found the solution variable $\phi$ for each representative cell length, a curve can be fitted to the data and $\phi$ can be extrapolated at $h=0$ (an infinitely fine mesh).

A power law function is used since CFD codes are not quite second-order accurate:
$$
\phi = \phi_0+ch^p
$$

- $p=2$ implies a perfect mesh, $p<2$ implies real meshes

Write this for two meshes:

$$
\phi_1 = \phi_0+c{h_1}^p\qquad \phi_2 = \phi_0+c{h_2}^p
$$

Combine the equations by eliminating $c$ and rearranging for $\phi_0$

$$
c=\frac{\phi_1-\phi_0}{{h_1}^p}
$$

$$
\phi_0 = \frac{(h_2/h_1)^p\phi_1-\phi_2}{(h_2/h_1)^p-1}
$$

Introduce refinement ratio $r_{21} = h_2/h_1$

$$
\phi_0 = \frac{r_{21}^p\phi_1-\phi_2}{r_{21}^p-1}
$$

### Quantifiying Error

Relative error:

$$
e_{21}=\bigg|\frac{\phi_2-\phi_1}{\phi_1}\bigg|
$$

Compares error between fine mesh and medium mesh

Better to use extrapolated relative error:

$$
e^\text{extra}_{21}=\bigg|\frac{\phi_1-\phi_0}{\phi_0}\bigg|
$$

Compares fine mesh to infinitely fine mesh

Grid Convergence Index:

$$
GCI_{21}=\frac{1.25e_{21}}{r^p-1}
$$

An improvement upon relative error

