# Jacobian

Consider the concept of local linearity. When looking at a nonlinear function, it will begin to look linear once zoomed in enough.

## Matrix

For a nonlinear matrix transformation, the Jacobian matrix represents the equivalent linear transformation observed when zoomed in and local linearity is present.

In 2D:

$$
\mathbf{J}=\begin{bmatrix}\frac{\partial f_1}{\partial x}&\frac{\partial f_1}{\partial y}\\\frac{\partial f_2}{\partial x}&\frac{\partial f_2}{\partial y}\end{bmatrix}
$$

## Determinant



$$
|\mathbf{J}|=\begin{vmatrix}\frac{\partial f_1}{\partial x}&\frac{\partial f_1}{\partial y}\\\frac{\partial f_2}{\partial x}&\frac{\partial f_2}{\partial y}\end{vmatrix}=\frac{\partial f_1}{\partial x}\frac{\partial f_2}{\partial y}-\frac{\partial f_1}{\partial y}\frac{\partial f_2}{\partial x}
$$