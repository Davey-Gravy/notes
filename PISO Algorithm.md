# PISO Algorithm
*From [Fluid Mechanics 101](https://www.youtube.com/watch?v=ahdW5TKacok) on YouTube*

**P**ressure-**I**mplicit **S**plitting of **O**perators

## Background 

- For solving the incompressible [[Navier-Stokes Equations]]

$$
\nabla\cdot\boldsymbol{U}=0
$$

$$
\frac{\partial\boldsymbol{U}}{\partial t}+\nabla\cdot(\boldsymbol{UU})=\frac{-1}{\rho}\nabla p+\mu\nabla^2\boldsymbol{U}+\boldsymbol{g}
$$

- 4 equations and 4 unknowns ($p, U_x, U_y, U_z$)
	- no equation for pressure --> pressure-velocity coupling issue
		- can't use ideal gas law for incompressible flows
	- continuity acts a restriction on the momentum field

## Setup

Write the momentum equations in matrix form:

$$
\boldsymbol{\mathcal{M}U}=-\nabla p
$$

- $\boldsymbol{\mathcal{M}}$ - matrix of coefficients found by discretizing the momentum equations with the [[Finite Volume Method]]

$$
\begin{bmatrix}M_{1,1}&M_{1.2}&\dots&M_{1,n} \\ M_{2,1}&M_{2,2}&\dots&M_{2,n} \\ \vdots&\vdots&\ddots&\vdots \\ M_{n,1}&M_{n,2}&\dots&M_{n,n}\end{bmatrix}\begin{bmatrix}U_1 \\ U_2 \\ \vdots \\ U_n\end{bmatrix}=\begin{bmatrix}(\partial p/\partial x)_1 \\ (\partial p/\partial x)_2 \\ \vdots \\ (\partial p/\partial x)_n\end{bmatrix}
$$

This matrix equation is solved using the pressure from the previous iteration, called the ***momentum predictor*** stage

- pressure gradient is an explicit source term 
- resulting velocity field $\boldsymbol{U}$ does not satisfy continuity
	- must be corrected

Then perform a diagonal decomposition of $\boldsymbol{\mathcal{M}}$:

$$
\boldsymbol{\mathcal{M}}=\begin{bmatrix}M_{1,1}&M_{1.2}&\dots&M_{1,n} \\ M_{2,1}&M_{2,2}&\dots&M_{2,n} \\ \vdots&\vdots&\ddots&\vdots \\ M_{n,1}&M_{n,2}&\dots&M_{n,n}\end{bmatrix}\quad\boldsymbol{\mathcal{A}}=\begin{bmatrix}M_{1,1}&0&\dots& 0\\0&M_{2,2}&\dots&0\\\vdots&\vdots&\ddots&0\\0&0&\dots&M_{n,n}\end{bmatrix}
$$

- Diagonal matrices are easily inverted

$$
\boldsymbol{\mathcal{A}}^{-1}=\begin{bmatrix}1/M_{1,1}&0&\dots& 0\\0&1/M_{2,2}&\dots&0\\\vdots&\vdots&\ddots&0\\0&0&\dots&1/M_{n,n}\end{bmatrix}
$$

We can now write:

$$
\boldsymbol{\mathcal{M}U}=\boldsymbol{\mathcal{A}U}-\boldsymbol{\mathcal{H}}
$$

$$
\boldsymbol{\mathcal{H}}=\boldsymbol{\mathcal{A}U}-\boldsymbol{\mathcal{M}U}
$$

Where $\boldsymbol{\mathcal{H}}$ contains the off-diagonal terms of $\boldsymbol{\mathcal{M}}$

- needed to calculated the source term for the pressure equation
- can rearrange for $\boldsymbol{U}$ by multiplying by $\boldsymbol{\mathcal{A}}^{-1}$

Now we can derive an equation for pressure:

$$
\boldsymbol{\mathcal{A}U}-\boldsymbol{\mathcal{H}}=-\nabla p
$$

Multiply both sides by $\boldsymbol{\mathcal{A}}^{-1}$ and rearrange:

$$
\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{A}U}=\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}}-\boldsymbol{\mathcal{A}}^{-1}\nabla p
$$

$$
\boldsymbol{U}=\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}}-\boldsymbol{\mathcal{A}}^{-1}\nabla p
$$

Then substitute into the continuity equation:

$$
\nabla\cdot\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}}-\boldsymbol{\mathcal{A}}^{-1}\nabla p=0
$$

$$
\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\nabla p)=\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}})
$$

## Algorithm

1. Solve the momentum predictor:

$$
\boldsymbol{\mathcal{M}U}=-\nabla p
$$

- extract the diagonal matrix $\boldsymbol{\mathcal{A}}$ from $\boldsymbol{\mathcal{M}}$ and compute $\boldsymbol{\mathcal{H}}$

$$
\boldsymbol{\mathcal{H}}=\boldsymbol{\mathcal{A}U}-\boldsymbol{\mathcal{M}U}
$$

2. Solve the pressure equation

$$
\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\nabla p)=\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}})
$$

3. Correct the velocity field to satisfy continuity

$$
\boldsymbol{U}=\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}}-\boldsymbol{\mathcal{A}}^{-1}\nabla p
$$

- Since velocity has been corrected, the pressure equation is no longer satisfied, since the source term $\boldsymbol{\mathcal{H}}$ depends on $\boldsymbol{U}$
	- can update $\boldsymbol{\mathcal{H}}$ in two ways:
		1. The [[SIMPLE Algorithm]]
			- Repeat each step every time
				- "outer corrector loops"
		2. The PISO Algorithm
			- Solve the momentum predictor only once
				-  Perform "inner loops" until the pressure equation converges
				-  Repeating the outer corrector loop to convergence for each time step too expensive

1. Solve momentum corrector

$$
\boldsymbol{\mathcal{M}U}=-\nabla p
$$

2. Perform inner loop

$$
\begin{gather}\boldsymbol{\mathcal{H}}=\boldsymbol{\mathcal{A}U}-\boldsymbol{\mathcal{M}U}\\\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\nabla p)=\nabla\cdot(\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}})\\\boldsymbol{U}=\boldsymbol{\mathcal{A}}^{-1}\boldsymbol{\mathcal{H}}-\boldsymbol{\mathcal{A}}^{-1}\nabla p\end{gather}
$$

### Under-Relaxation

- If time step is sufficiently small $(Co <1)$
	- 1 momentum predictor + 2 inner correctors for partial convergence
	- Under-relaxation not needed since $Co<1$ --> strong diagonal dominance

### Non-Orthogonal Correctors

If the mesh is non-orthogonal, the pressure equation requires additional iterations 