### ODE Example
**x** is the size of a population of bunnies. The rate of change of its growth is proportional to its size in time:
$$
\frac{d\mathbf{x}}{dt}=\dot{\mathbf{x}}=\lambda\mathbf{x}
$$
Separate variables and integrate:

$$
\frac{dx}{dt}=\lambda x\longrightarrow\frac{dx}{x}=\lambda\,dt
$$
$$
\int\frac{dx}{x}=\int\lambda\,dt
$$
$$
\ln x(t)=\lambda t+c
$$
$$
x(t)=e^{\lambda t+c}=e^{\lambda t}K,\qquad K\, const
$$
How to find *K*? Use [[initial condition]], plug into $x(t)$:
$$
x(0)=e^0K=K
$$
Finally:
$$
x(t)=e^{\lambda t}x(0)
$$