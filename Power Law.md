$$
\frac{df}{dx}=nx^{n-1}
$$
$$
\begin{align}
\frac{df}{dx}&\approx\frac{1}{\Delta x}\left[\left(x+\Delta x\right)^n-x^n\right]
\\
&\approx\frac{1}{\Delta x}\left[\cancel{x^n}+nx^{n-1}\Delta x+\frac{n(n-1)}{2}x^{n-2}\Delta x^2+O(\Delta x^3)-\cancel{x^n}\right]
\\
&\approx\frac{1}{\Delta x}\left[nx^{n-1}\Delta x+\frac{n(n-1)}{2}x^{n-2}\Delta x^2+O(\Delta x^3)\right]
\\
&\approx \boxed{nx^{n-1}+\cancel{O(\Delta x)}}
\end{align}
$$
