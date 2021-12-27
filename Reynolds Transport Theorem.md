# Reynolds Transport Theorem

Method to switch from ***system*** analysis to ***control volume*** analysis

- System:  collection of matter of fixed identity
	- same set of particles
	- specific quantity of matter
- Control volume: a fixed volume in space that particles pass through
	- independent of mass

General form:

$$
\frac{D\phi_{sys}}{Dt}=\underbrace{\frac{\partial}{\partial t}\int_{CV}\phi\rho dV}_{\substack{\text{rate of change of }\phi \\ \text{ in CV}}}+\underbrace{\int_{CS}\phi\rho (\vec{u}\cdot\vec{n})dA}_{\substack{\text{net flux of }\phi\\\text{ across CS}}}=0
$$

Conservation of mass:

$$
\frac{Dm_{sys}}{Dt}=\frac{\partial}{\partial t}\int_{CV}\rho dV+\int_{CS}\rho (\vec{u}\cdot\vec{n})dA=0
$$

Conservation of momentum:

- inertial reference frame

$$
\Sigma \vec{F}=\frac{\partial}{\partial t}\int_{CV}\vec{u}\rho dV+\int_{CS}\vec{u}\rho(\vec{u}\cdot\vec{n})dA
$$

- non-inertial reference frame $xyz$

$$
\Sigma \vec{F}-\int_{CV}\vec{a}_{rf}\rho dV=\frac{\partial}{\partial t}\int_{CV}\vec{U}_{xyz}\rho dV+\int_{CS}\vec{U}_{xyz}\rho(\vec{U}_{xyz}\cdot\vec{n})dA
$$

Conservation of energy:

$$
\dot{Q}-\dot{W}_{sh}-\dot{W}_{vs}=\frac{\partial}{\partial t}\int_{CV}(\tilde{u}+u^2/2+gz)\rho dV+\int_{CS}(h+u^2/2+gz)\rho(\vec{u}\cdot\vec{n})dA
$$

