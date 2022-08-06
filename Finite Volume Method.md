# Finite Volume Method

- In terms of CFD codes

We have the [[Navier-Stokes Equations]]:

$$
\frac{\partial(\rho\boldsymbol{U})}{\partial t}+\nabla\cdot(\rho \boldsymbol{UU})=-\nabla p+\nabla\cdot\big[\mu\big((\nabla\boldsymbol{U})+(\nabla\boldsymbol{U}^T)\big)\big]-\frac{2}{3}\mu(\nabla\cdot\boldsymbol{U})\boldsymbol{I}+\rho\boldsymbol{g}
$$

and want to write them in matrix form to use the [[SIMPLE Algorithm]] or [[PISO Algorithm]]:

$$
\mathcal{M}\boldsymbol{U}=\boldsymbol{B}
$$

For simplicity, consider the steady, incompressible Navier-Stokes equations:

$$
\nabla\cdot(\boldsymbol{UU})=-\frac{1}{\rho}\nabla p+\nabla\cdot(\nu\nabla\boldsymbol{U})+\boldsymbol{g}
$$

These will be discretized using a 3D polyhedral cell
- Flow variables ($p$, $T$, $\boldsymbol{U}$) vary  linearly across the cell
	- values calculated at the cell centroid $P$
- Owner and neighbor cells (with centroid $N$)
	- generally, owner cells will have $M$ neighbors
## Integration

Integrate the Navier-Stokes equations over the volume of the cell:

$$
\int_V\bigg[\nabla\cdot(\boldsymbol{UU})+\frac{1}{\rho}\nabla p-\nabla\cdot(\nu\nabla\boldsymbol{U})-\boldsymbol{g}\bigg]dV=0
$$

Split the integral:

$$
\int_V[\nabla\cdot(\boldsymbol{UU})]\,dV=\int_V\bigg[-\frac{1}{\rho}\nabla p\bigg]\,dV+\int_V[\nabla\cdot(\nu\nabla\boldsymbol{U})]\,dV+\int_V\boldsymbol{g}\,dV
$$

### Source Terms

The gravity integral is simple, evaluating to:

$$
\int_V\boldsymbol{g}\,dV=\boldsymbol{g}V_P
$$

This is treated an independent source term, and is added to the right hand side of the matrix equation ($\boldsymbol{B}$)

Source terms that vary linearly with velocity must be treated differently:

$$
\nabla\cdot(\boldsymbol{UU})=-\frac{1}{\rho}\nabla p+\nabla\cdot(\nu\nabla\boldsymbol{U})+\boldsymbol{g}+\underbrace{S\boldsymbol{U}}
$$

Again, integrate over the cell volume:

$$
\int_V[S\boldsymbol{U}]\,dV=S_P\int_V\boldsymbol{U}\,dV
$$

Recall that the velocity varies linearly across the cell:

$$
\begin{gather}
S_P\int_V\boldsymbol{U}\,dV=S_P\int_V\big[\boldsymbol{U}_P+\underbrace{(\boldsymbol{x-x}_P)}_{\substack{\text{distance from}\\\text{centroid}}}\,*\,(\nabla\boldsymbol{U}_P)\big]\,dV\\
=S_P\boldsymbol{U}_P\int_VdV+\cancel{\int_V(\boldsymbol{x-x}_P)\,dV}\,*\,(\nabla\boldsymbol{U}_P)\\
=S_P\boldsymbol{U}_PV_P
\end{gather}
$$

####  Implicit and Explicit Treatment

- can either add $-S_PV_P$ to the $\mathcal{M}$ matrix (implicit treatment)
	-  if $S_P$ is negative, term is added to the diagonal terms, makes solution more stable (diagonal dominance)
- or add $S_P\boldsymbol{U}_PV_P$ to the $\boldsymbol{B}$ matrix (explicit treatment)

$$
\mathcal{M}=\begin{bmatrix}
-S_1V_1 & 0 & \dots & 0 \\
0 & -S_2V_2 & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & -S_MV_M
\end{bmatrix}
$$

$$
\mathcal{B}=\begin{bmatrix}
S_1\boldsymbol{U}_1V_1 \\ S_2\boldsymbol{U}_2V_2 \\
\vdots \\ S_M\boldsymbol{U}_MV_M
\end{bmatrix}
$$

#### Mixed Implicit-Explicit Treatment

If source term looks like:

$$
S\boldsymbol{U}^2
$$

we rewrite as:

$$
(S\boldsymbol{U}^{i-1})\,*\,\boldsymbol{U}
$$

and the integral becomes:

$$
\int_VS\boldsymbol{U}^2dV=S_P\boldsymbol{U}_P^{i-1}\boldsymbol{U}_P
$$

where $\boldsymbol{U}^{i-1}$ is the value from the previous iteration, which linearizes the source term

## Convection and Diffusion Terms

- More difficult due to divergence operator $\nabla\cdot$
- Will consider just convection term
	- diffusion term requires orthogonal correctors

Consider [[Gauss Divergence Theorem|Gauss's divergence theorem]]:

$$
\int_V\nabla\cdot\boldsymbol{F}dV=\int_S\boldsymbol{F}\cdot\hat{\boldsymbol{n}}\,dS
$$

Use the divergence theorem on the convection term:

$$
\int_V[\nabla\cdot\boldsymbol{UU}]\,dV=\int_S[\boldsymbol{U}\underbrace{(\boldsymbol{U}\cdot\hat{\boldsymbol{n}})}_{\substack{\text{volume flow}\\\text{rate}}}]\,dS
$$

The $\boldsymbol{U}$ outside the dot product is the unknown velocity

Then write the integral for each face:

$$
\int_S[\boldsymbol{U}(\boldsymbol{U}\cdot\hat{\boldsymbol{n}})]\,dS=\sum_{i=1}^M\int_S\boldsymbol{U}_i(\boldsymbol{U}_i\cdot\hat{\boldsymbol{n}}_i)\,dS_i
$$

- Variation across faces is linear
	- approximate as the value at the face center ($f$)
	
$$
\sum_{i=1}^M\int_S\boldsymbol{U}_i(\boldsymbol{U}_i\cdot\hat{\boldsymbol{n}}_i)\,dS_i\approx\sum_{i=1}^M\boldsymbol{U}_{fi}(\boldsymbol{U}_{fi}\cdot\hat{\boldsymbol{n}})S_i
$$

- Eliminates the integral

Recall that flow variable values are stored at the cell centroids ($P$, $N$)
- [[Discretization Schemes]] (interpolation) are needed to get a value for face centers ($f$)
	- upwind
	- second-order/linear upwind
	- central differencing
	- QUICK
- schemes calculate face values using owner and neighbor cell centroids

Convection term can finally be written as:

$$
\int_V[\nabla\cdot\boldsymbol{UU}]\,dV\approx\sum_{i=1}^M\boldsymbol{U}_{fi}F_{fi}
$$

Leads to both diagonal and off-diagonal terms in the $\mathcal{M}$ matrix
- cell with 6 neighbors will have one diagonal term, 6 off-diagonal terms
