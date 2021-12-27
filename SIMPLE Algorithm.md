# SIMPLE Algorithm
- **S**emi-**I**mplicit **M**ethod for **P**ressure-**L**inked **E**quations
- Intended to solve the steady-state [[Navier-Stokes Equations]]

$$
\nabla\cdot \boldsymbol{U} = 0
$$

$$
\boldsymbol{U}\cdot\nabla\boldsymbol{U}-\nabla\cdot(\nu\nabla\boldsymbol{U})=-\nabla p
$$

- 4 equations for 4 unknowns ($U_x$, $U_y$, $U_z$, $p$)
	- $p = p/\rho$ (kinematic pressure)

## Why is this system difficult to solve?
- have equations for $U_x$, $U_y$, and $U_z$, but not $p$
- velocities $U_x$, $U_y$, and $U_z$ must satisfy continuity
- convection term $\nabla\cdot(\boldsymbol{U}\boldsymbol{U})$ is non-linear
- pressure cannot be found using an equation of state (ideal gas law) since density and temperature may be constant

The SIMPLE algorithm is a procedure to:
1. Derive a pressure equation from the momentum and continuity equations
2. Derive a corrector for the velocity field to ensure continuity is satsified
## Deriving the Equations
Rewrite the momentum equations in matrix form:

$$
\boldsymbol{\mathcal{M}}\boldsymbol{U}=-\nabla p
$$

- coefficients of $\boldsymbol{\mathcal{M}}$ found when discretizing the equation
	- all coeffs are known

Example (x-component of momentum equation):

$$
\begin{bmatrix}
M_{11} & M_{12} & \dots & M_{1n}\\
M_{21} & M_{22} & \dots & M_{2n}\\
\vdots & \vdots & \ddots & \vdots\\
M_{n1} & M_{n2} & \dots & M_{nn}
\end{bmatrix}
\begin{bmatrix}
U_1 \\ U_2\\ \vdots \\ U_n
\end{bmatrix}
=
\begin{bmatrix}
(\partial\rho/\partial x)_1 \\ (\partial\rho/\partial x)_2 \\
\vdots \\ (\partial\rho/\partial x)_n
\end{bmatrix}
$$

- $n$ equations, one for each cell centroid
- all $M_{ij}$ are known

Separate the matrix of coefficients $\boldsymbol{\mathcal{M}}$ into diagonal and off-diagonal components:

$$
\boldsymbol{\mathcal{M}}\boldsymbol{U}=\boldsymbol{\mathcal{A}}\boldsymbol{U}-\boldsymbol{\mathcal{H}}=-\nabla p
$$

- $\boldsymbol{\mathcal{A}}$ is a diagonal matrix:
 
$$
\boldsymbol{\mathcal{A}}=\begin{bmatrix}
A_{11} & 0 & \dots & 0 \\
0 & A_{22} & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & A_{nn}
\end{bmatrix}
$$

- diagonal matrices are easy to invert
 
$$
\boldsymbol{\mathcal{A}}^{-1}=\begin{bmatrix}
1/A_{11} & 0 & \dots & 0 \\
0 & 1/A_{22} & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & 1/A_{nn}
\end{bmatrix}
$$
 
 - $\boldsymbol{\mathcal{H}}$ is found using the off-diagonal terms and velocity from the previous iteration:

$$
\boldsymbol{\mathcal{H}}=\boldsymbol{\mathcal{A}}\boldsymbol{U}-\boldsymbol{\mathcal{M}}\boldsymbol{U}
$$

Now a pressure equation can be derived by rearranging the momentum equation:
$$
\boldsymbol{\mathcal{A}}\boldsymbol{U}-\boldsymbol{\mathcal{H}}=-\nabla p
$$

$$
\boldsymbol{U} = \boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}}-\boldsymbol{\mathcal{A}}^{-1}\nabla p
$$

Then substitute into the continuity equation:

$$
\nabla\cdot\boldsymbol{U}=0
$$

$$
\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}}-\mathcal{A}^{-1}\nabla p)=0
$$

This results in a Poisson equation for pressure:

$$
\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\nabla p)=\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}})
$$

Our 4 equations are then:

$$
\boxed{\begin{align}\boldsymbol{\mathcal{M}}\boldsymbol{U}&=-\nabla p \\
\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\nabla p)&=\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}})
\end{align}}
$$

## Solution Process

1. Solve the momentum equations for the uncorrected velocity field

$$
\boldsymbol{\mathcal{M}}\boldsymbol{U}=-\nabla p
$$

2. Solve the Poisson equation for the pressure field

$$
\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\nabla p)=\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}})
$$

3. Correct the velocity field using the pressure field so that continuity is satisfied

$$
\boldsymbol{U} = \mathcal{A}^{-1}\mathcal{H}-\mathcal{A}^{-1}\nabla p
$$

4. Repeat, now that the velocity field does not satisfy the momentum equations
	- referred to as "outer corrector" loops

Can be done for other parameters (energy, turbulence, species transport, etc.)


## Under-Relaxation



## Final Thoughts
- SIMPLE algorithm called a "*pressure-based*" algorithm
	- use an equation of state to calculate density (if flow is non-isothermal)
- "*density-based*" algorithms are preferred for compressible flow
	- density is computed directly from the continuity equation, equation of state is used to compute pressure