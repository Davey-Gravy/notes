# OpenFOAM Discretization Schemes

## Time

- backward: transient second order
- bounded
- CoEuler
- CrankNicolson: transient second order
	- uses a blending factor $\psi$
		- $\psi = 0$ --> pure Euler
		- $\psi =1$ --> pure Crank-Nicolson
- Euler: transient first order, bounded
- localEuler
- SLTS
- steadyState: steady simulations (simpleFoam)

## Convective Terms

- upwind: first order
- linearUpwind: second order, bounded
- linearUpwindV: second order, bounded, for vector fields
- linear: second order, unbounded
- limitedLinear: second order, bounded, more stable than linear
	- recommended for LES

## Gradient Terms

- edgeCellsLeastSquares
- fourth
- Gauss
- leastSquares
- pointCellsLeastSquares

Syntax:

$\text{grad(U)}\quad\text{Gauss}\quad\text{linear};$

## Laplacian Terms

- corrected
	- for meshes with grading and non-orthogonality
- faceCorrected
- limited
- linearFit
- orthogonal
	- mainly limited to perfect hex meshes with no grading
- quadraticFit
- uncorrected
	- for meshes with very low non-orthogonality
	- more diffusive than limited and corrected

## Recommended Setup

```c++
ddtSchemes
{
	default		CrankNicolson	0;
}
gradSchemes
{
	default		cellLimited Gauss linear 0.5;
	grad(U)		cellLimited Gauss linear 1;
}
divSchemes
{
	default			none;
	div(phi,U)		Gauss linearUpwindV grad(U);
	div(phi,omega)	Gauss linearUpwind	default;
	div(phi,k)		Gauss linearUpwind	default;
	div((nuEff*dev(T(grad(U)))))	Gauss linear;
}
laplacianSchemes
{
	default		Gauss linear limited 1;
}
interpolationSchemes
{
	default		linear;
}
snGradSchemes
{
	default		limited 1;
}
```
- Very similar to setup of commercial solvers
- Second order accurate, fully bounded
- Should change blending factor of **laplacianSchemes** and **snGradSchemes** based on mesh quality
- Use a CFL number < 2 to minimize time diffusion