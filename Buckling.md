# Buckling

A part experiencing uniaxial compressive [[Stress|stress]] will buckle when load exceeds its ***critical load*** $P_\text{crit}$.

Characteristics of buckling:

- sudden deformation
- large displacements

## Euler's Buckling Formula


> $$
> P_\text{crit}=\frac{\pi^2EI}{L_e^2}
> $$
> 
> -- Leonhard Euler (1707-1783, Switzerland)

$E$ - Young's modulus
$I$ - [[Second Moment of Area|area moment of inertia]]
$L_e$ - effective length
- distance between inflection points
	- column pinned at both ends: $L_e=L$
	- fixed at one end, free on the other: $L_e=2L$
	- fixed at one end, roller on the other: $L_e=0.5L$
	- pinned at one end, roller on the other: $L_e=0.7L$

Can divide by area to achieve critical stress:

$$
\sigma_\text{crit}=\frac{\pi^2EI}{AL_e^2}
$$

Introducing the radius of gyration $r=\sqrt{I/A}$:

$$
\sigma_\text{crit}=\frac{\pi^2EI}{(L_e/r)^2}
$$

$L_e/r$ - effective slenderness ratio

Maximum compressive stress calculated using the ***secant formula***:

$$
\sigma_\text{max}=\frac{P}{A}\left[1+
\frac{ec}{r^2}\sec\left(\frac{L}{2r}\sqrt{\frac{P}{EA}}\right)\right]
$$