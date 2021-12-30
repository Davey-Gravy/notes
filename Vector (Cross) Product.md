# Vector (cross) Product

Results in a ***vector*** perpendicular to the two vectors used

- Measures how much two vectors point in different directions
- Can be interpreted as the area of the parallelogram formed by the two vectors used
- consequently only works in 3D

$$
\begin{align}\vec{a}\times\vec{b}=(&a_x\hat{i}+a_x\hat{j}+a_z\hat{k})\times(b_x\hat{i}+b_y\hat{j}+b_z\hat{k})\\=\,&a_xb_x\hat{i}\times\hat{i}+a_xb_y\hat{i}\times\hat{j}+a_xb_z\hat{i}\times\hat{k}
\end{align}
$$

$$
\begin{matrix}\hat{i}\times\hat{i}=0 & \hat{j}\times\hat{i}=-\hat{k}&\hat{k}\times\hat{i}=\hat{j}\\
\hat{i}\times\hat{j}=\hat{k}&\hat{j}\times\hat{j}=0&\hat{k}\times\hat{j}=-\hat{i}\\\hat{i}\times\hat{k}=-\hat{j}&\hat{j}\times\hat{k}=\hat{i}&\hat{k}\times\hat{k}=0\end{matrix}
$$

Computed using the [[Determinant|determinant]]

$$
\begin{gather}\vec{a}\times\vec{b}=(a_yb_z-a_zb_y)\,\hat{i}+(a_zb_x-a_xb_z)\,\hat{j}+(a_xb_y-a_yb_x)\,\hat{k}\\=\begin{vmatrix}\hat{i}&\hat{j}&\hat{k}\\a_x&a_y&a_z\\b_x&b_y&b_z\end{vmatrix}
\end{gather}
$$

- magnitude given by:

$$
|\vec{a}\times\vec{b}|=|\vec{a}||\vec{b}|\sin\theta
$$