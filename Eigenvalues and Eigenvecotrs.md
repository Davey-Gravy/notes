# Eigenvalues and Eigenvectors
## Definition: 
Let $A$ be an $n\times n$ matrix. A scalar $\lambda$ is an eigenvalue of $A$ if a nonzero vector $\bar{x}$ exists such that $A\bar{x}=\lambda\bar{x}$. Such a vector $\bar{x}$ is called an eigenvector of $A$ corresponding to $\lambda$.

## Intuition
An eigenvector is a vector that remains on its original span after a linear transformation. Eigenvalues represent the scaling factor experienced by the linear transformation.
$$\overbrace{A\bar{x}}^{\text{matrix-vector multiplication}}=\underbrace{\lambda\bar{x}}_\text{scalar multiplication}$$

### Computation
To work out difference between matrix-vector multiplication and scalar multiplication, rewrite right hand side as matrix-vector multiplication:
$$\lambda = \begin{bmatrix}\lambda&0\\0&\lambda\end{bmatrix}=\lambda\begin{bmatrix}1&0\\0&1\end{bmatrix}=\lambda I$$
$$A\bar{x}=(\lambda I)\bar{x}$$
$$A\bar{x}-(\lambda I)\bar{x}=\bar{0}$$
$$(A-\lambda I)\bar{x}=\bar{0}$$
Because we want a non-zero $\bar{x}$, the only way for matrix-vector multiplication to result in zero is for the [[Determinant|determinant]] to be equal to zero:
$$\det(A-\lambda I)=0$$
$$\begin{vmatrix}a_{11}-\lambda&0\\0&a_{22}-\lambda\end{vmatrix}=[(a_{11}-\lambda)(a_{22}-\lambda)]-[0(0)]=0$$
## Examples:
Show that $x=\begin{bmatrix}2 \\ 1 \end{bmatrix}$ is an eigenvector of $A=\begin{bmatrix}3&2\\3&-2\end{bmatrix}$ corresponding to $\lambda = 4$
$$A\bar{x}=\lambda\bar{x}$$
$$\begin{bmatrix}3&2\\3&-2\end{bmatrix}\begin{bmatrix}2\\1\end{bmatrix}=4\begin{bmatrix}2\\1\end{bmatrix}$$
$$[3(2)+2(1)]+[3(2)+(-2)(1)]=4(2)+4(1)$$
$$8+4=8+4$$
$$12=12$$