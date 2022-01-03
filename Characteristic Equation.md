# Characteristic Equation

We can use the general form of a first order homogeneous ODE to inspire a solution for the $n$-th order version.

$$
\alpha_1\frac{dy}{dt}
+\alpha_0y=0$$

The general solution to this is:

$$
y = Ce^{-\frac{\alpha_0}{\alpha_1}t}
$$

If we assume $y=Ce^{\lambda t}$ and plug this into the $n$-th order equation, we get:

$$
\alpha_n\frac{d^n}{dt^n}Ce^{\lambda t}+\alpha_{n-1}\frac{d^{n-1}}{dt^{n-1}}Ce^{\lambda t}+\dots+\alpha_1\frac{d}{dt}Ce^{\lambda t}+\alpha_0Ce^{\lambda t}=0
$$

Simplifying derivatives:

$$
\alpha_n\lambda^nCe^{\lambda t}+\alpha_{n-1}\lambda^{n-1}Ce^{\lambda t}+\dots+\alpha_1\lambda Ce^{\lambda t}+\alpha_0Ce^{\lambda t}=0
$$

Finally, canceling out $Ce^{\lambda t}$ yields:

$$
\alpha_n\lambda^n+\alpha_{n-1}\lambda^{n-1}+\dots\alpha_1\lambda+\alpha_0=0
$$

This is known as the characteristic equation/polynomial of the ODE. Finding the roots of this equation provides viable values for $\lambda$ in our solution. 

## Repeated Roots

- [[Reduction of Order]]

## Complex Roots

