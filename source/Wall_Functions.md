# Wall Functions
Boundary layer results in a varying gradient depending on proximity to the wall. This gradient is important for determining wall shear stress $\tau_w$ and wall heat flux $q_w$, given by:$$\frac{\tau_w}{\rho} = -\nu\frac{\partial U}{\partial y}\Bigg\rvert_{y=0}\qquad \frac{q_w}{\rho c_p} = -\alpha\frac{\partial T}{\partial y}\Bigg|_{y=0}$$

As Reynolds number &uparrow;, boundary layer thickness &downarrow;, computing time &uparrow;

If the mesh is sufficiently fine, these gradients can be captured, but if the mesh is coarse, there will be gradient error

If producing a fine enough mesh is not possible, wall functions or wall treatment is applied, which modifies the near wall kinematic viscosity *&nu;* or the near wall thermal diffusivity *&alpha;* to correct the wall shear stress or wall heat flux

CFD code assumes linear variation of velocity and temperature:$$\tau_w = -\rho\nu_w\frac{U_p}{y_p}\qquad q_w = -\rho c_p\alpha_w\bigg(\frac{T_p-T_w}{y}\bigg)$$

Experimental measurements of near wall velocity (a) and temperature (b):
![[wall_measurements.png]]

Velocity profile represented by piecewise function:$$U^+=\begin{cases}y^+ &y^+ < 11.25 \\ \frac{1}{\kappa}\log(Ey^+) &y^+ > 11.25\end{cases}$$$$\kappa = 0.4187\quad E = 9.793$$
Temperature profile varies between different fluids, introduce the Prandtl number
$$T^+=\begin{cases}Pr\hspace{2pt} y^+ & y^+<y_L^+ \\ Pr_t\big(\frac{1}{\kappa}\log(Ey^+)+P\big) & y^+ > y_L^+\end{cases}$$

Molecular Prandtl number $Pr = \nu/\alpha$

$$P = 9.24\bigg[\bigg(\frac{Pr}{Pr_t}\bigg)^{3/4}-1\bigg](1+0.28e^{-0.007Pr/Pr_t})$$
![[wall_measurements_approximation.png]]
$y^+$ should be < 5 or > 30 due to inaccuracy in the buffer region

## $y^+$ and $y^*$
Dimensionless velocity and temperature profiles are needed for generality across different flow scenarios:$$U^+ = \frac{U}{u_\tau} \qquad T^+ = \frac{(T_w-T_p)\rho c_pu_\tau}{q_w}$$

The friction velocity $u_\tau$ can be expressed in terms of the wall shear stress ($y^+$) or the turbulent kinetic energy ($y^*$)
$$u_\tau = \sqrt{\frac{|\tau_w|}{\rho}}\qquad u_\tau = \sqrt{C_\mu^{1/2}k}\quad C_\mu = 0.09$$$$y^+, y^* = \frac{\rho u_\tau y}{\mu}$$
The final wall function for kinematic viscosity:$$\nu_w = \begin{cases} \nu & y^+ < 11.25 \\ \nu\Big(\frac{y^+}{\frac{1}{\kappa}\log(Ey^+)}\Big) & y^+ > 11.25\end{cases}$$

#theory