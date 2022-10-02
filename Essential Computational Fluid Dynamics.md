# Fundamentals
## Governing Equations of Fluid Dynamics and Heat Transfer
- Conservation of chemical species (mass)
- Conservation of momentum (Newton's second law)
- Conservation of energy (1st law of thermodynamics)

Concept of continuous medium consisting of elementary volumes
- Lagrangian approach
	- equations formulated wrt individual particle
- Eulerian approach
	- equations formulated wrt to distributed properties

### Material Derivative
Consider element with velocity $\boldsymbol{V}(x,y,z,t)$ in fluid with density of $\rho(x,y,z,t)$
- Differentiation of $\rho$ wrt $t$ yields:$$\frac{\partial\rho}{\partial t}+\frac{\partial\rho}{\partial x}\frac{dx(t)}{dt}+\frac{\partial\rho}{\partial y}\frac{dy(t)}{dt}+\frac{\partial\rho}{\partial z}\frac{dz(t)}{dt}=\frac{\partial\rho}{\partial t}+u\frac{\partial\rho}{\partial x}+v\frac{\partial\rho}{\partial y}+w\frac{\partial\rho}{\partial z}$$
- Right hand side is the material derivative$$\frac{D\rho}{Dt}=\frac{\partial\rho}{\partial t}+u\frac{\partial\rho}{\partial x}+v\frac{\partial\rho}{\partial y}+w\frac{\partial\rho}{\partial z}=\frac{\partial\rho}{\partial t}+\boldsymbol{V}\cdot\nabla\rho$$
- Derivative has two parts:
	1. Time varying part at given location
	2. Part due to motion of element

Volume changes as result of flow:$$\frac{1}{\delta\mathcal{V}}\frac{d(\delta\mathcal{V})}{dt}=\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}+\frac{\partial w}{\partial z}=\nabla\cdot \boldsymbol{V}$$

### Mass Conservation
Consider fluid element $\delta\mathcal{V}$
- mass $\delta m=\rho\delta\mathcal{V}$ must be constant$$\frac{d(\rho\delta\mathcal{V})}{dt}=\delta\mathcal{V}\frac{D\rho}{Dt}+\rho\frac{d(\delta\mathcal{V})}{dt}=0$$
Divide by $\delta\mathcal{V}$ to get the *continuity equation*:$$\frac{1}{\delta\mathcal{V}}\frac{d(\delta\mathcal{V})}{dt}=\frac{D\rho}{Dt}+\rho\nabla\cdot \boldsymbol{V} = 0$$
Can be rewritten as:$$\frac{\partial\rho}{\partial t} + V\cdot\nabla\rho+\rho\nabla\cdot \boldsymbol{V} = \frac{\partial\rho}{\partial t} + \nabla\cdot(\rho \boldsymbol{V}) = 0$$
For incompressible fluid:$$\nabla\cdot V=0$$
### Conservation of Chemical Species
Transport via diffusion quantified by $\boldsymbol{J}_i(x,t)$
- denotes direction and rate of mass flux of species *i*
- movement from high concentration to lower concentration
	- measured with 
		- *mass fraction* $m_i(x,t)$, mass ratio of species *i* to mass of element
		- *concentration of species* $C_i=m_i\rho$. mass of species *i* per unit volume
- Conservation given by:$$\frac{\partial}{\partial t}(\rho m_i)+\nabla\cdot(\rho m_i\boldsymbol{V}+\boldsymbol{J}_i) = R_i$$
	- $R_i$ is a source term to account for production/consumption of species by chemical reactions

#### Fick's Law of Diffusion
Empirical relation, used when variations of concentration are not very strong$$\boldsymbol{J}_i=-\Gamma_i\nabla m_i$$
- Concentration becomes:$$\frac{\partial}{\partial t}(\rho m_i)+\nabla\cdot(\rho m_i\boldsymbol{V}) = R_i+\nabla\cdot(\Gamma_i\nabla m_i)$$
- If diffusion coefficients $\Gamma_i$ are constants:$$\frac{\partial}{\partial t}(\rho m_i)+\nabla\cdot(\rho m_i\boldsymbol{V}) = R_i+\Gamma_i\nabla^2 m_i$$

### Conservation of Momentum
Newton's second law:$$\frac{d}{dt}(m\boldsymbol{V})=\boldsymbol{F}$$
- Replace normal derivative with material derivative:$$\rho\frac{D}{Dt}(\boldsymbol{V})=\rho\bigg[\frac{\partial}{\partial t}(\boldsymbol{V})+(\boldsymbol{V}\cdot\nabla)\boldsymbol{V}\bigg]$$

Two types of forces that affect fluid elements:
1. Body forces
	- act directly on the element, come from external source
	- gravity, electric, magnetic, etc.
	- total body force is proportional to its mass, written as $\rho\boldsymbol{f}$
2. Surface forces
	- pressure and friction between neighboring fluid elements and walls
	- vector field of surface forces can represented by 3x3 stress tensor $\tau$
		- component $\tau_{ij}$ is the *i*-component of stress acting normal to the *j*-axis
		- diagonal elements cause extension/contraction of the fluid element, offdiagonal elements represent deformation by shear

Conservation of momentum written as:$$\rho\frac{Du}{Dt}=\rho f_x+\frac{\partial\tau_{xx}}{\partial x}+\frac{\partial\tau_{yx}}{\partial y}+\frac{\partial\tau_{zx}}{\partial z}$$$$\rho\frac{Dv}{Dt}=\rho f_y+\frac{\partial\tau_{xy}}{\partial x}+\frac{\partial\tau_{yy}}{\partial y}+\frac{\partial\tau_{zy}}{\partial z}$$$$\rho\frac{Dw}{Dt}=\rho f_z+\frac{\partial\tau_{xz}}{\partial x}+\frac{\partial\tau_{yz}}{\partial y}+\frac{\partial\tau_{zz}}{\partial z}$$

Stress tensor can separated into isotropic presure (always present) and viscous friction (zero if fluid at rest):$$\tau_{ij}=-p\delta_{ij}+\sigma_{ij}$$$$\delta_{ij}=\begin{cases} 1\quad\text{if}\quad i=j \\ 0\quad\text{if}\quad i\neq j\end{cases}$$

Model for viscous stresses:$$\sigma_{ij}=\lambda\delta_{ij}(\nabla\cdot\boldsymbol{V})+\mu\bigg(\frac{\partial u_i}{\partial x_j}+\frac{\partial u_j}{\partial x_i}\bigg)$$
- $\mu$ and $\lambda$ are first and second viscosity coefficients
- for incompressible fluid, $\lambda$ disappears
- for compressible fluid, $\lambda=-\frac{2}{3}\mu$ is general approximation

Final form of momentum conservation, Navier-Stokes equations:$$\begin{align}\rho\frac{Du}{Dt}=\rho f_x-\frac{\partial p}{\partial x}+&\frac{\partial}{\partial x}\bigg[\mu\bigg(-\frac{2}{3}\nabla\cdot\boldsymbol{V}+2\frac{\partial u}{\partial x}\bigg)\bigg]\\+&\frac{\partial}{\partial y}\bigg[\mu\bigg(\frac{\partial v}{\partial x}+\frac{\partial u}{\partial y}\bigg)\bigg]+\frac{\partial}{\partial z}\bigg[\mu\bigg(\frac{\partial w}{\partial x}+\frac{\partial u}{\partial z}\bigg)\bigg]
\end{align}$$$$\begin{align}\rho\frac{Dv}{Dt}=\rho f_y-\frac{\partial p}{\partial y}+&\frac{\partial}{\partial y}\bigg[\mu\bigg(-\frac{2}{3}\nabla\cdot\boldsymbol{V}+2\frac{\partial v}{\partial y}\bigg)\bigg]\\+&\frac{\partial}{\partial x}\bigg[\mu\bigg(\frac{\partial v}{\partial x}+\frac{\partial u}{\partial y}\bigg)\bigg]+\frac{\partial}{\partial z}\bigg[\mu\bigg(\frac{\partial w}{\partial y}+\frac{\partial v}{\partial z}\bigg)\bigg]
\end{align}$$$$\begin{align}\rho\frac{Dw}{Dt}=\rho f_z-\frac{\partial p}{\partial z}+&\frac{\partial}{\partial z}\bigg[\mu\bigg(-\frac{2}{3}\nabla\cdot\boldsymbol{V}+2\frac{\partial w}{\partial z}\bigg)\bigg]\\+&\frac{\partial}{\partial x}\bigg[\mu\bigg(\frac{\partial w}{\partial x}+\frac{\partial u}{\partial z}\bigg)\bigg]+\frac{\partial}{\partial y}\bigg[\mu\bigg(\frac{\partial w}{\partial y}+\frac{\partial v}{\partial z}\bigg)\bigg]
\end{align}$$

Can be simplified by introducing rate of strain tensor:$$S_{ij}=\frac{1}{2}\bigg(\frac{\partial u_i}{\partial x_j}+\frac{\partial u_j}{\partial x_i}\bigg)$$
$$\rho\frac{Du_i}{Dt}=\rho f_i -\frac{\partial p}{\partial x_i}+\frac{\partial}{\partial x_j}\bigg[2\mu S_{ij}-\frac{2}{3}\mu(\nabla\cdot\boldsymbol{V})\delta_{ij}\bigg]$$
For incompressible fluid, constant viscosity $\mu$:$$\rho\frac{D\boldsymbol{V}}{Dt}=-\nabla p+\mu\nabla^2\boldsymbol{V}+\rho\boldsymbol{f}$$
For inviscid fluid, $\mu = \lambda = 0$, results in the Euler equations:$$\rho\frac{D\boldsymbol{V}}{Dt}=-\nabla p+\rho\boldsymbol{f}$$
### Conservation of Energy
$$\rho\frac{De}{Dt}=-\nabla\cdot\boldsymbol{q}-p(\nabla\cdot\boldsymbol{V})+\dot{Q}$$
- $e(x,t)\quad$internal energy per unit mass
- $\boldsymbol{q}(x,t)\quad$vector field of heat flux by thermal conduction
	- represented by Fourier's law:$$\boldsymbol{q}=-\kappa\nabla T$$
		- $T(x,t)\quad$temperature field
		- $\kappa\quad$thermal conductivity
- $\dot{Q}\quad$rate of internal heat generation, caused by friction, radiation, etc.

Neglect internal heat generation, assume incompressible (Boussinesq approximation):$$\rho C\frac{DT}{Dt}=\rho C\bigg(\frac{\partial T}{\partial t}+\boldsymbol{V}\cdot\nabla T\bigg)=\nabla\cdot(\kappa\nabla T)$$
Reduces to classical heat conduction equation if $\kappa$ constant:$$\rho C\frac{\partial T}{\partial t} = \kappa\nabla^2T$$
### Equation of State
Ideal gas model:$$\frac{p}{\rho}=RT,\quad e=e(T)$$
Incompressible fluid model:$$\rho=const, \quad e=CT$$
### Equations in Integral Form
Conservation of mass:$$\frac{d}{dt}\int_\Omega\rho d\Omega+\int_S\rho\boldsymbol{V}\cdot\boldsymbol{n}dS =0$$
- $\Omega\quad$control volume
- $S\quad$boundary of control volume

Conservation of momentum:$$\frac{d}{dt}\int_\Omega\rho u d\Omega+\int_S\rho u\boldsymbol{V}\cdot\boldsymbol{n}dS=\int_S\boldsymbol{t}_x\cdot\boldsymbol{n}dS+\int_\Omega\rho f_xd\Omega$$$$\frac{d}{dt}\int_\Omega\rho v d\Omega+\int_S\rho v\boldsymbol{V}\cdot\boldsymbol{n}dS=\int_S\boldsymbol{t}_y\cdot\boldsymbol{n}dS+\int_\Omega\rho f_yd\Omega$$$$\frac{d}{dt}\int_\Omega\rho w d\Omega+\int_S\rho w\boldsymbol{V}\cdot\boldsymbol{n}dS=\int_S\boldsymbol{t}_z\cdot\boldsymbol{n}dS+\int_\Omega\rho f_zd\Omega$$
Full Navier-Stokes for the *i*-component of momentum:
$$\begin{align}&\frac{d}{dt}\int_\Omega\rho u_id\Omega+\int_S\rho u_i\boldsymbol{V}\cdot\boldsymbol{n}dS\\&=\int_S\bigg[(-p+\lambda\nabla\cdot\boldsymbol{V})n_i+\sum_j\mu\bigg(\frac{\partial u_i}{\partial x_j}+\frac{\partial u_j}{\partial x_i}\bigg)n_j\bigg]dS+\int_\Omega\rho f_id\Omega\end{align}$$
Conservation of energy:
- must consider both conduction ($\boldsymbol{q}\cdot\boldsymbol{n}$) and convection ($\rho E\boldsymbol{V}$)$$\begin{align}\frac{d}{dt}&\int_\Omega\rho Ed\Omega+\int_S\boldsymbol{q}\cdot\boldsymbol{n}dS+\int_S\rho E\boldsymbol{V}\cdot\boldsymbol{n}dS\\&=\int_S-p\boldsymbol{V}\cdot\boldsymbol{n}dS+\int_\Omega\dot{Q}d\Omega+\int_\Omega\rho\boldsymbol{f}\cdot\boldsymbol{V}d\Omega\end{align}$$
- using Boussinesq assumption:$$\frac{d}{dt}\int_\Omega\rho CTd\Omega+\int_S\rho CT\boldsymbol{V}\cdot\boldsymbol{n}dS=\int_S\kappa\nabla T\cdot\boldsymbol{n}dS$$

Different integral types:
- ***Convective flux***: surface integrals that don't contain derivatives of the conserved field
	- represent transport by velocity through the boundary of the control volume
- ***Diffusive flux***: surface integrals that contain first derivatives of the conserved field
	- represent transport by diffusion, conduction, or viscosity
- ***Volume source***: correspond to distributed sources or sinks of the conserved quantity within the control volume
- ***Surface force***: represent work by normal surface forces on boundary of the control volume

Illustrated in conservation of an arbitrary scalar field $\Phi$:$$\underbrace{\frac{d}{dt}\int_\Omega\Phi d\Omega}_\text{Rate of change}+\underbrace{\int_S\Phi\boldsymbol{V}\cdot\boldsymbol{n}dS}_\text{Convective flux}=\underbrace{\int_S\mathcal{X}\nabla\Phi\cdot\boldsymbol{n}dS}_\text{Diffusive flux}+\underbrace{\int_\Omega Qd\Omega}_\text{Volume source}$$