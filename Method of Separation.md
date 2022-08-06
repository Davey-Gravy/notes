# Method of Separation

Can be performed on ***separable*** equations:

$$
F(y,x)=M(y)\,N(x)
$$

$F(y,x)$ can be separated into a function of $x$ alone and a function of $y$ alone.

## Generally

Separate variables into terms:

$$
\frac{1}{M(y)}\frac{dy}{dx}=N(x)
$$

Then integrate:

$$
\int\frac{1}{M(y)}\frac{dy}{\cancel{dx}}\,\cancel{dx}=\int N(x)\,dx
$$

$$
\int\frac{1}{M(y)}dy=\int N(x)\,dx
$$

## Example

Separate variables into separate terms:

$$
\begin{align} 
\frac{dy}{dt}+2ty&=0\\
\frac{1}{y}\frac{dy}{dt}+2t&=0
\end{align}
$$

Then integrate:

$$
\begin{align} 
\int\frac{1}{y}\frac{dy}{dt}+2t\,dt&=\int0\,dt\\
\int\frac{1}{y}\frac{dy}{dt}\,dt+\int2t\,dt&=\int0\,dt\\
\int\frac{1}{y}\frac{dy}{\cancel{dt}}\,\cancel{dt}+t^2+c_1&=c_2
\end{align}
$$

$$
\begin{gather}
\ln|y|=\hat{c}-t^2\\
|y|=e^{\hat{c}-t^2}=e^\hat{c}e^{-t^2}
\end{gather}
$$