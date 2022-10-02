The study of [[Fluids|fluids]] at rest (fluid statics) and in motion (fluid dynamics)

- [[Stokes Streamfunction]]

# Fluid Statics

Governing equation:

$$
-\nabla p+\rho\vec{g}=0
$$

If we choose a Cartesian coordinate system with the $z$ axis oriented upward. this reduces to 

$$
\frac{dp}{dz}=-\rho g
$$

To find pressure variation, boundary conditions are applied and the equation is integrated:

$$
\int_{p_0}^pdp=-\int_{z_0}^z\rho g\,dz
$$

$$
p-p_0=-\rho g(z-z_0)=\rho g(z_0-z)
$$

Measuring height $h$ downward as $h=z_0-z$:

$$
\Delta p=\rho gh
$$

## Buoyancy

Archimedes' Principle

Archimedes (c. 287-212 BC, Greece)

Consider a cube with side length $d$ that is submerged in a fluid. What is the net force acting on the cube?

$$
P=\frac{F}{A}\quad P=\rho gh
$$

$$
\begin{align}
F_{net}&=P_{bottom}d^2-P_{top}d^2\\
&=(P_{bottom}-P_{top})d^2\\
&=\big[(\cancel{\rho gh}+\rho gd)-\cancel{\rho gh}\big]d^2\\
&=\rho gd^3\\
&=\rho gV\\
&=mg
\end{align}
$$

The net force acting on the cube is equal to the weight of the liquid displaced by the cube, and is called the ***buoyant force***

# Fluid Dynamics
- [[Reynolds Transport Theorem]]
- [[Reynolds Number]]
- [[Computational Fluid Dynamics (CFD)]]
- [[Potential Flow]]

