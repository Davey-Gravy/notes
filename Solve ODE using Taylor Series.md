[[Ordinary Differential Equations (ODEs)|ODE]]:
>$$
\dot{x}=ax\Longrightarrow x(t)=e^{at}x(0)
$$

Use [[Taylor Series|Taylor series]]:
> $$x(t)=c_0+c_1t+c_2t^2+\dots\underbrace{O(t^3)}_{\substack{\text{higher-order}\\\text{terms}}}$$

Take [[Derivative|derivative]]:

$$
\dot{x}(t)=0+c_1+2c_2t+3c_3t+4c_4t^4+\dots\underbrace{O(t^4)}_{\substack{\text{higher-order}\\\text{terms}}}
$$

Going term-by-term by powers of t:
$$
\begin{align}
t^0:&&c_1=ac_0 \\
t^1:&&2c_2=ac_1 \\
t^2:&&3c_3=ac_2\\
t^3:&&4c_4=ac_3\\
t^n:&&nc_n=ac_{n-1}
\end{align}
$$

Use initial condition $x(0)=x_0$:
$$
\begin{align}
t^0:&&c_1&=ac_0=ax_0 \\
t^1:&&2c_2&=ac_1\longrightarrow c_2=\frac{a^2x_0}{2}\\
t^2:&&3c_3&=ac_2\longrightarrow c_3=\frac{a^3x_0}{3!}\\
t^n:&&nc_n&=ac_{n-1}\longrightarrow c_n=\frac{a^nx_0}{n!}
\end{align}
$$

Plug into Taylor series expansion:

$$
\begin{align}
x(t)&=x_0+ax_0\,t+\frac{a^2x_0}{2}t^2+\dots\\
&=x_0\left(1+at+\frac{(at)^2}{2!}+\dots\right)\\
&=\boxed{e^{at}}
\end{align}
$$

Extend to matrices:
$$
\dot{\mathbf{x}}=\mathbf{Ax}\Longrightarrow\mathbf{x}(t)=e^{\mathbf{A}t}\mathbf{x}(0)
$$
Is basis of all numerical approximations in this course

Discretize:
A function $f(x+\Delta x)$ can be Taylor expanded at a point $x$
$$
f\left(x+\Delta x\right)=f(x)+f'(x)\Delta x+f''(x)\Delta x^2 + \dots
$$

Can vary $x$ and $\Delta x$ 