Method of compactly writing vector operations
- repeated indices indicate a summation over components

# Traditional vector notation --> Index notation

Vectors

$$
\vec{u}=u\hat{i}+v\hat{j}+w\hat{k}=(u_x,u_y,u_z)=(u,v,w)
$$

$$
\vec{u}=u_i
$$

Gradient:

$$
\nabla \longrightarrow\frac{\partial}{\partial x_i}=\bigg(\frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial}{\partial z}\bigg)
$$

$$
\nabla T\longrightarrow\frac{\partial T}{\partial x_i}=\bigg(\frac{\partial T}{\partial x},\frac{\partial T}{\partial y},\frac{\partial T}{\partial z}\bigg)
$$

Divergence:

$$
\nabla\cdot\vec{u}\longrightarrow\frac{\partial u_i}{\partial x_i}=\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}+\frac{\partial w}{\partial z}
$$

Curl:

$$
\nabla\times\vec{u}=\begin{vmatrix}\hat{i}&\hat{j}&\hat{k}\\\frac{\partial}{\partial x}&\frac{\partial}{\partial y}&\frac{\partial}{\partial z}\\u&v&w\end{vmatrix}
$$

Kroenecker delta:

$$
\delta_{ij}=\begin{cases}1&\text{if }i=j\\-1&\text{if }i\neq j\end{cases}\qquad\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}
$$

# Example

Material derivative:

$$
\begin{align}
\frac{D\rho}{Dt}&=\frac{\partial\rho}{\partial t}+u_j\frac{\partial\rho}{\partial x_j}\\
&=\frac{\partial\rho}{\partial t}+u\frac{\partial\rho}{\partial x}+v\frac{\partial\rho}{\partial y}+w\frac{\partial\rho}{\partial z}
\end{align}
$$
