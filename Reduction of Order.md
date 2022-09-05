# Reduction of Order

- Effective on any linear [[Ordinary Differential Equations (ODEs)|ODE]]
- Finds secondary solutions of an ODE given that we found one solution

Uses the product of a known solution and a "helper" function. By substituting this product into the differential equation and applying the product rule repeatedly, all terms of the undifferentiated function cancel, leaving behind a lower order equation for the first derivative of the helper function, which can then by solved and integrated to find the exact value of the helper function.

## Example

Assuming $p$, $q$, and $r$ are given, continuous functions, we have:

$$
p(t)y''+q(t)y'+r(t)y=0
$$

We assume that we have one solution $y_1(t)$. Another solution can be found with the form:

$$
y_2=u(t)y_1(t)
$$

Then differentiate and plug into the original differential equation:

$$
\begin{align}
y'_2&=u'y_1+uy'_1\\
y''_2&=u''y_1+2u'y'_1+uy''_1
\end{align}
$$

$$
\begin{align}
p(t)y_2''+q(t)y_2'+r(t)y_2&=0\\
p(t)\left[u''y_1+2u'y'_1+uy''_1\right]+q(t)\left[u'y_1+uy'_1\right]+r(t)uy_1&=0
\end{align}
$$

Now rearrange in terms of derivatives of $u$:

$$
p(t)y_1u''+2\left[2py'_1+q(t)y_1\right]u'+\left[p(t)y''_1+q(t)y'_1+r(t)y_1\right]u=0
$$

Because $y_1$ is a solution to the original differential equation, the coefficient of $u$ is zero, yielding:

$$
p(t)y_1u''+\left[2py'_1+q(t)y_1\right]u'=0
$$

This is now a first order equation in $u'$, and can be written in terms of $u$:

$$
\begin{align}
\frac{u''}{u'}&=-\frac{\left[2py'_1+q(t)y_1\right]}{y_1p(t}\\
\int\frac{u''}{u'}dt&=\int-\frac{\left[2py'_1+q(t)y_1\right]}{y_1p(t}dt\\
\ln(u')&=\int-\frac{\left[2py'_1+q(t)y_1\right]}{y_1p(t}dt\\
u&=\int \exp\left(\int-\frac{\left[2py'_1+q(t)y_1\right]}{y_1p(t}dt\right)\,dt
\end{align}
$$