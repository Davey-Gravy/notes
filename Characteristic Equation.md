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

Consider  the following second order, constant coefficient ODE:

$$
y''+y=0,\quad y(0)=\alpha,\quad y'(0)=\beta
$$

Substituting the exponential guess $y=Ce^{\lambda t}$ results in the characteristic polynomial

$$
\lambda^2+1=0
$$

which has complex conjugate roots $\lambda=\pm i$

Our general solution becomes a copmlex function:

$$
y=K_1e^{it}+K_ 2e^{-it}
$$

with $K_1$ and $K_2$ being potentially complex coefficients. To split the exponentials into real and imaginary parts, the power series representation is used:

$$
e^x=1+x+\frac{x^2}{2}+\frac{x^3}{3!}+\dots
$$

Substituting $x=it$:

$$
\begin{align}
e^{it}&=1+it-\frac{t^2}{2}+\frac{t^3}{3!}+\dots\\
&=\left(1-\frac{t^2}{2}+\frac{t^4}{4!}-\frac{t^6}{6!}-\dots\right)+i\left(t-\frac{t^3}{3!}+\frac{t^5}{5!}-\dots\right)
\end{align}
$$

This results in the Euler identity:

$$
e^{it}=\cos(t)+i\sin(t)
$$

and similarly:

$$
e^{-it}=\cos(t)-i\sin(t)
$$

Selecting $K_1,\,K_2=\frac{1}{2}$, we find:

$$
y_1=\cos(t)
$$

While selecting $K_1=\frac{i}{2}$ and $K_2=-\frac{i}{2}$ results in:

$$
y_2=\sin(t)
$$

We can now generalize that for a second order, linear, constant coefficient, homogeneous ODE with complex roots $\lambda=\mu\pm i\sigma$:

$$
\boxed{y=C_1e^{\mu t}\cos(\sigma t)+C_2e^{\mu t}\sin(\sigma t)}
$$