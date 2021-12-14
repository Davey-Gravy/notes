# Vectors
Definition --> a quantity with both ***magnitude*** and ***direction***
- force, acceleration, momentum, etc.
## Notation
Indicated by an arrow: $\vec{F}$
- Concurrent
	- go through the same point
- Coplanar
	- exist in the same plane
- Resultant
	- combination
### Unit Vectors
- Vectors with magnitude 1 that indicate direction
	- $x$ direction: $\hat{i}$
	- $y$ direction: $\hat{j}$
	- $z$ direction: $\hat{k}$

$$\vec{a}=6\hat{i}+2\hat{j}+7\hat{k}$$
### Matrix Form
May also be represented as a vector:
$$\vec{a}=6\hat{i}+2\hat{j}+7\hat{k}=\begin{bmatrix}6\\2\\7 \end{bmatrix}$$
## Operations
### Magnitude
$$|\vec{a}|=\sqrt{6^2+2^2+7^2}=\sqrt{89}\approx9.43$$
Generally:
$$|\vec{F}|=\sqrt{\sum_iF_i^2}$$
### Addition
Three primary methods
1. Parallelogram law
	- two vectors can be added by creating a parallelogram from them
	- the resulting diagonal is the sum of the vectors
2. Tip-to-tail
	- place the tail of one vector onto the tip of the other one
	- the sum is given by the line connecting the tail of the first vector and the tip of the second vector
3. Vector decomposition
	- break the vectors into their Cartesian components, then sum together

Vector addition is ***associative***:
$$\vec{a}+\vec{b}=\vec{b}+\vec{a}$$
### Subtraction
Subtraction of vectors is simply the addition of a negative component

In the cases of (1) and (2) above, simply reverse the direciton of the vector you intend on subtracting and proceed
### Multiplication
#### Scalar (dot) Product
Results in a ***scalar***
$$\vec{a}\cdot\vec{b}=|\vec{a}||\vec{b}|\cos\theta$$
$$\vec{a}=3\hat{i}+5\vec{j},\quad\vec{b}=4\hat{i}+8\hat{j}$$
$$\vec{a}\cdot\vec{b}=(3\hat{i}+5\vec{j})\cdot(4\hat{i}+8\hat{j})=12+40 = 52$$
- Can be used to find angle between two vectors
$$\cos\theta=\frac{\vec{a}\cdot\vec{b}}{|\vec{a}||\vec{b}|}=\frac{52}{\sqrt{3^2+5^2}\sqrt{4^2+8^2}}\approx\frac{52}{52.15}$$
$$\theta=\cos^{-1}\bigg(\frac{52}{52.15}\bigg)\approx4.40^\circ$$
- Also ***associative***
$$\vec{a}\cdot\vec{b}=\vec{b}\cdot\vec{a}$$
- and ***distributive***
$$x\vec{a}\cdot\vec{b}=\vec{a}\cdot x\vec{b}=x(\vec{a}\cdot\vec{b})$$
#### Vector (cross) Product
Results in a ***vector***
$$\begin{align}\vec{a}\times\vec{b}=(&a_x\hat{i}+a_x\hat{j}+a_z\hat{k})\times(b_x\hat{i}+b_y\hat{j}+b_z\hat{k})\\=\,&a_xb_x\hat{i}\times\hat{i}+a_xb_y\hat{i}\times\hat{j}+a_xb_z\hat{i}\times\hat{k}
\end{align}$$
$$\begin{matrix}\hat{i}\times\hat{i}=0 & \hat{j}\times\hat{i}=-\hat{k}&\hat{k}\times\hat{i}=\hat{j}\\
\hat{i}\times\hat{j}=\hat{k}&\hat{j}\times\hat{j}=0&\hat{k}\times\hat{j}=-\hat{i}\\\hat{i}\times\hat{k}=-\hat{j}&\hat{j}\times\hat{k}=\hat{i}&\hat{k}\times\hat{k}=0\end{matrix}$$
$$\begin{align}\vec{a}\times\vec{b}&=(a_yb_z-a_zb_y)\,\hat{i}+(a_zb_x-a_xb_z)\,\hat{j}+(a_xb_y-a_yb_x)\,\hat{k}\\&=\begin{vmatrix}\hat{i}&\hat{j}&\hat{k}\\a_x&a_y&a_z\\b_x&b_y&b_z\end{vmatrix}
\end{align}$$
- magnitude given by:
$$|\vec{a}\times\vec{b}|=|\vec{a}||\vec{b}|\sin\theta$$
