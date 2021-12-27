# Discretization Schemes

## Background

- CFD codes compute values at the cell centroids
- We need the value at the face centers
- "Face interpolation schemes"
- Boundary faces and internal faces must be treated differently
	- only considering *internal faces*
	- can use [[Wall Functions|wall functions]] for boundary faces

## Analysis

- General quantity $\phi$ is known at the owner cell centroid ($\phi_P$) and the neighbor cell centroid ($\phi_N$)
- Want to know the quantity at the face center ($\phi_f$)

### Linear/Central Differencing

- $\psi$ - ratio of distance between owner cell $P$ and face center $f$ and owner cell $P$ and neighbor cell $N$

$$
\psi=\frac{|\boldsymbol{x}_f-\boldsymbol{x}_P|}{|\boldsymbol{x}_N-\boldsymbol{x}_P|}\qquad 0\leq\psi\leq 1
$$

$$
\phi_f=\psi\phi_N+(1-\psi)\phi_P
$$

- Linear interpolation of $\phi$ across cell face
	- *second-order accurate*
	- *unbounded* scheme
		- prone to oscillations
- Used for the diffusion term of [[Navier-Stokes Equations]]

$$
\frac{\partial\boldsymbol{U}}{\partial t}+\nabla\cdot(\boldsymbol{UU})=-\frac{1}{p}+\underbrace{\nu\nabla^2\boldsymbol{U}}+\boldsymbol{g}
$$

- Do not use for the convection term in [[Reynolds Averaged Navier-Stokes (RANS)|RANS]] solvers

$$
\frac{\partial\boldsymbol{U}}{\partial t}+\underbrace{\nabla\cdot(\boldsymbol{UU})}=-\frac{1}{p}+\nu\nabla^2\boldsymbol{U}+\boldsymbol{g}
$$

- Can be used for the convection term in [[Large Eddy Simulation (LES)|LES]], accuracy needed

### Upwind Schemes

Value of $\phi_f$ depends on direction of mass flux

$$
F_f=\rho_fA_f(\boldsymbol{U}_f\cdot\hat{\boldsymbol{n}})
$$

$$
\phi_f=\begin{cases}
\phi_P&\text{if } F_f >0\quad\text{mass flow out of cell}\\
\phi_N&\text{if } F_f <0\quad\text{mass flow into cell}
\end{cases}
$$

- $F_f > 0$ - mass flow out of cell
- $F_f < 0$ - mass flow into cell
$$$$
 - $\phi$ does not vary linearly across the cell face
	 - $\phi$ remains constant between cell centroid and cell face
	 - *first-order accurate*
		 - smears out solution, may not see fine flow details

Inaccurate, but is the most stable scheme for convection dominated flows

### Linear Upwind Differencing
A more accurate upwind differencing scheme
- uses the gradient of $\phi$

$$
\phi_f=\begin{cases}
\phi_P+(\nabla\phi)_P\cdot\boldsymbol{r}&\text{if } F_f >0\\
\phi_N+(\nabla\phi)_N\cdot\boldsymbol{r}&\text{if } F_f <0
\end{cases}
$$

- Variation between cell centroid and cell face is linear
	- *second-order accurate*
- Popular for the convection term

#### Gradient Limiters

Gradient often limited to prevent local maxima/minima
If gradient is too large, the quantity at the face $\phi_f$ can be greater or less than both owner and neighbor cell centroid values $\phi_P$ and $\phi_N$
- this is non-physical
- results in oscillations

$$
\phi_f=\phi_P+\varphi(\nabla\phi)_P\cdot\boldsymbol{r}\qquad0\leq\varphi\leq1
$$
- $\varphi$ used to limit the gradient ($\nabla\phi$)

## Advanced Schemes

Often use a combination of:
1. Linear/central differencing for accuracy ($\phi_{CD}$)
2. Upwind differencing for stability ($\phi_{UD}$)

$$
\phi_f = \Psi\phi_{UD}+(11-\Psi)\phi_{CD}
$$

- $\Psi$ is a blending function that switches between schemes
	- $\Psi$ may vary throughout the mesh 
		- use central differencing for stable areas of solution
		- upwind differencing for oscillating areas

