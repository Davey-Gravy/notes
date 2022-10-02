Rewriting a differential equation so that a perfect derivative is formed, making integration trivial.

Employs the use of a "helper function" called the ***integrating factor*** to create a [[Product Rule|product rule]] structure on one side of the equation.

# Derivation

Consider the non-separable differential equation below:

$$
\begin{align}
\frac{dy}{dt}+p(t)\,y&=q(t)\\
y'+py&=q
\end{align}
$$

To reach product rule structure, multiply  both sides by a helper function $\mu$:

$$
\mu y'+\mu py=\mu q
$$

Notice that $\mu'=\mu p$ satisifies product rule structure:

$$
\mu y'+\mu py=\mu y'+\mu'y=\frac{d}{dt}(\mu y)
$$

so we first solve this using the [[Method of Separation|method of separation]]:

$$
\begin{align}
\frac{d\mu}{dt}&=\mu p\\
\frac{1}{\mu}\frac{d\mu}{dt}&=p\\
\int\frac{1}{\mu}d\mu&=\int p\,dt\\
\ln|\mu|&=\int p\,dt\\
\mu &= e^{\int p\,dt}
\end{align}
$$

Then we plug $\mu'=\mu p$ back into the original differential equation:

$$
\begin{align}
\mu y'+\mu'y&=\mu q\\
\frac{d(\mu y)}{dt}&=\mu q\\
\int\frac{d(\mu y)}{dt}dt&=\int\mu q\,dt\\
\mu y&=\int\mu q\,dt
\end{align}
$$

While we need a form of $q$ to fully solve the equation, we can rearrange for $y$, giving us the general solution to this differential equation:

$$
y(t)=\frac{\int\mu q\,dt}{\mu}
$$

## General Procedure

1. Convert equation into  the standard form used in the derivation. Identify $p(t)$ and $q(t)$, ensuring the appropriate sign is used.
2. Integrate $p(t)$ to find an appropriate integrating factor
3. Multiply the differential equation by the integrating factor and integrate both sides, which leads to the following form:

$$
\mu y = \int\mu q(t)\,dt
$$

4. Complete the integration prcoess, apply initial conditions, and solve for $y$