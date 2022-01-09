## Definitions

**State**: the smallest set of variables that can represent a system for all $t>0$



State equation:

$$
\begin{align}
\dot{\mathbf{x}}&=\mathbf{Ax}+\mathbf{Bu}\\
\mathbf{y}&=\mathbf{Cx}+\mathbf{Du}
\end{align}
$$

$$
\begin{alignat}{3}
\mathbf{x}&=\begin{bmatrix}x_1\\x_2\\\vdots\\x_n\end{bmatrix}\quad\mathbf{A}&&=\begin{bmatrix}a_{11}&a_{12}&\dots&a_{1n}\\a_{21}&a_{22}&\dots&a_{2n}\\\vdots&\vdots&\ddots&\vdots\\a_{n1}&a_{n2}&\dots&a_{nn}\end{bmatrix}\quad\mathbf{B}&&=\begin{bmatrix}b_{11}&b_{12}&\dots&b_{1r}\\b_{21}&b_{22}&\dots&b_{2r}\\\vdots&\vdots&\ddots&\vdots\\b_{n1}&b_{n2}&\dots&b_{nr}\end{bmatrix}\quad\mathbf{u}=\begin{bmatrix}u_1\\u_2\\\vdots\\u_r\end{bmatrix}\\
\mathbf{y}&=\begin{bmatrix}y_1\\y_2\\\vdots\\y_n\end{bmatrix}\quad\mathbf{C}&&=\begin{bmatrix}c_{11}&c_{12}&\dots&c_{1n}\\c_{21}&c_{22}&\dots&c_{2n}\\\vdots&\vdots&\ddots&\vdots\\c_{m1}&c_{m2}&\dots&c_{mn}\end{bmatrix}\quad\mathbf{D}&&=\begin{bmatrix}d_{11}&d_{12}&\dots&d_{1r}\\d_{21}&d_{22}&\dots&d_{2r}\\\vdots&\vdots&\ddots&\vdots\\d_{m1}&d_{m2}&\dots&d_{mr}\end{bmatrix}
\end{alignat}
$$

* $\mathbf{A}$ - state matrix
* $\mathbf{B}$ - input matrix
* $\mathbf{C}$ - output matrix
* $\mathbf{D}$ - direct transmission matrix