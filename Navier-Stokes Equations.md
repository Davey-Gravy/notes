# Navier-Stokes
Newton's 2<sup>nd</sup> law ($\vec{F} = m\vec{a}$) for a fluid

Assuming Newtonian fluid:

$$
\underbrace{\frac{\partial \vec{u}}{\partial t}}_{\text{unsteady}}+\underbrace{(\vec{u}\cdot\nabla)\vec{u}}_{\text{convective acceleration}}=\overbrace{-\nabla p}^{\text{pressure gradient}}+\overbrace{\nu\nabla^2\vec{u}}^{\text{viscous diffusion}}
$$

Euler equation, assumes incompressible ($\rho =$ constant), inviscid flow ($\nu = 0$):

$$\frac{\partial \vec{u}}{\partial t}+(\vec{u}\cdot\nabla)\vec{u}=-\nabla p
$$

May be written with material derivative:

$$
\rho\frac{D\vec{u}}{Dt}=-\nabla p+\mu\nabla^2\vec{u}
$$

## Differential Form

### Conservation of Mass

For a *system*:

$$
\frac{Dm_{sys}}{Dt}=0
$$

To extend this to a *control volume* we use the [[Reynolds Transport Theorem]]:

$$
\frac{\partial}{\partial t}\int_{CV}\rho dV+\int_{CS}\rho (\vec{u}\cdot\vec{n})dA=0
$$

Considering a small element $dxdydz$:

$$
\frac{\partial}{\partial t}\int_{CV}\rho dV=\frac{\partial\rho}{\partial t}dxdydz
$$

Net flux in $x$:

$$
\frac{\partial}{\partial x}(\rho u)dxdydz
$$

Substituting into RTT:

$$
\frac{\partial\rho}{\partial t}+\frac{\partial}{\partial x}(\rho u)+\frac{\partial}{\partial y}(\rho v)+\frac{\partial}{\partial z}(\rho w)=0
$$

Rewritten as:

$$
\frac{\partial\rho}{\partial t}+\nabla\cdot\rho\vec{u}=0
$$