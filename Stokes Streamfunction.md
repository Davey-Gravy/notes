# Stokes Streamfunction


Stokes streamfunction $\psi$ describes streamlines and flow velocity in three-dimensional incompressible flow with axisymmetry and is defined as:

$$
u =\frac{\partial\psi}{\partial y}\quad v=-\frac{\partial\psi}{\partial x}
$$

Using these in the [[Navier-Stokes Equations|Navier-Stokes equations]] and eliminating pressure results in:

$$
\frac{\partial}{\partial t}\nabla^2\psi+\frac{\partial\psi}{\partial y}\frac{\partial}{\partial x}\nabla^2\psi-\frac{\partial\psi}{\partial x}\frac{\partial}{\partial y}\nabla^2\psi=\nabla^4\psi
$$

System is reduced to one dependent variable $\psi$ and one equation, but is now fourth-order

Relationship between [[Vorticity|vorticity]] and streamfunction:

$$
\eta=\nabla^2\psi
$$