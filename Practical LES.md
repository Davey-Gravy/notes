# Practical LES
## Eddies
Turbulent flows contain *eddies* or vortices of varying scale and energy, which deviate from the mean flow

LES aims to resolve these eddies using a mesh

### How are Eddies Resolved?
- 4 cells minimum are needed to resolve an eddy
	- one for each direction
	- velocity known only at cell centroids
		- ***sub-grid scale*** model used for eddies of smaller size
- The mesh sets the minimum eddy size that can be resolved (implicit LES)
	- How size of eddies do we want to resolve --> How fine does the mesh need to be?

### Kolmogorov Turbulent Energy Cascade
#### Wavenumber $(k)$
- Spatial frequency of the eddy

$$
k = \frac{2\pi}{d}
$$

- smaller eddies have a higher wavenumber

Turbulent kinetic energy density of an eddy is proportional to its diameter, inversely proportional to wavenumber
- area under curve gives turbulent kinetic energy, used in [[Reynolds Averaged Navier-Stokes (RANS)|RANS]] simulations

Since the mesh doesn't resolve all eddies, not all of the turbulent kinetic energy is not resolved
- A good LES mesh resolves >80% of the turbulent kinetic energy
	- Remaining ~20% modeled by the sub-grid model

## Meshing
- Eddy size/energy varies through out the domain
	- Determine the ***integral length scale***	
		- length of an eddy corresponding to the average kinetic energy of all the eddies
		- Representative of all eddies at a given location

$$
l_0=\frac{\int_0^\infty k^{-1}E(k)d(k)}{\int_0^\infty E(k)d(k)}
$$

- larger integral length scale --> higher turbulent kinetic energy --> larger eddies --> larger cells
	- Calculated from a previous RANS calculation

$$
\underbrace{l_0=\frac{k^{3/2}}{\epsilon}}_{k-\epsilon}\qquad \underbrace{l_0=\frac{k^{1/2}}{C_\mu\omega}}_{k-\omega}
$$

- good estimate
	- 5 cells across integral length scale likely to resolve 80% of the turbulent kinetic energy

$$
\Delta=\frac{l_0}{5}
$$

- can also rearrange the above 

$$
f=\frac{l_0}{\Delta}
$$

- if $f < 5$ then mesh is too coarse and needs to be refined