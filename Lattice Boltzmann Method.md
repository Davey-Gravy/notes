Creates link between microscopic and macroscopic particles

Collection of microscopic particles described with a distribution function

Velocity and pressure computed as momentum of distribution functions

Only one unknown: distribution function

Grid must be fine enough to capture all collisions:
$$l_{mfp}\ll l_{avg}\ll l$$
Define distribution function:
$$f(\xi,\mathbf{x},t)$$
$$\xi=\frac{d\mathbf{x}}{dt}$$

Defines density of molecules with:
* velocity $\xi+d\xi$
* at location $\mathbf{x}+d\mathbf{x}$
* at time $t$


This allows *continuum* description at the *kinetic* level

Must conserve:
* mass
* momentum
on each collision

Take time derivative of $f(\mathbf{\xi}, \mathbf{x},t)$
$$
\begin{align}
\frac{df(\mathbf{\xi},\mathbf{x},t)}{dt}&=\left(\frac{\partial}{\partial t}+\frac{d\mathbf{x}}{dt}\frac{\partial}{\partial\mathbf{x}}+\frac{\partial\mathbf{\xi}}{\partial t}\frac{\partial}{\partial\mathbf{\xi}}\right)f(\mathbf{\xi},\mathbf{x},t) \\
&=\left(\frac{\partial}{\partial t}+\mathbf{\xi}\frac{\partial}{\partial\mathbf{x}}+\frac{\mathbf{f}}{\rho}\frac{\partial}{\partial\mathbf{\xi}}\right)f(\mathbf{\xi},\mathbf{x},t) \\
&=:\Omega(f)
\end{align}
$$

$\Omega(f)$ is the [[Collision Operator|collision operator]]

Evolution equation:
$$
\left(\frac{\partial}{\partial t}+\mathbf{\xi}\frac{\partial}{\partial\mathbf{x}}+\frac{\mathbf{f}}{\rho}\frac{\partial}{\partial\mathbf{\xi}}\right)=:\Omega(f)
$$

Can recover [[Navier-Stokes Equations]] given certain constraints