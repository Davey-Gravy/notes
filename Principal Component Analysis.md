# Principal Component Analysis

Order components with highest energy (amount of information)

Two definitions, same algorithm:
1. Orthogonal projection of data onto lower dimensional space ***principal subspace***
	- maximizes variance of projected data
2. Linear projection
	- minimize average projection cost
		- mean square distance between data and projections
		- find low dimensional space that represents observed data the best

## Maximum Variance Formulation
- Start with data set $\{\mathbf{x}_n\}_{n=1}^N$ with dimension $D$
- Project data into subspace with dimension $M<D$ while maximizing variance
- direction of subspace given as $\mathbf{u}_1$
	- assume $\mathbf{u}_1$ is unit --> $\mathbf{u}_1^T\mathbf{u}_1 = 1$ 
- Project data by taking inner product $\mathbf{u}_1^T\mathbf{x}_n$
- Sample mean given by: $$\bar{\mathbf{x}}_n = \frac{1}{N}\sum_{n=1}^N\mathbf{x}_n$$
	- Sample mean of projected data is $\mathbf{u}_1^T\bar{\mathbf{x}}_n$	
- Variance is then: 

$$
\frac{1}{N}\sum_{n=1}^N(\mathbf{u}_1^T\mathbf{x}_n - \mathbf{u}_1^T\bar{\mathbf{x}})^2 = \mathbf{u}_1^T\mathbf{Su}_1
$$

$$
\mathbf{S}=\frac{1}{N}\sum_{n=1}^N(\mathbf{x}_n-\bar{\mathbf{x}})(\mathbf{x}_n-\bar{\mathbf{x}})^T
$$

- **S** = covariance matrix
- Use Lagrangian multiplier, maximize: 
$$
\frac{\partial}{\partial u_1}\bigg[\mathbf{u}_1^T\mathbf{Su}_1+\lambda_1(1-\mathbf{u}_1^T\mathbf{u_1})\bigg] = 0
$$

$$
2\mathbf{Su}_1-2\lambda\mathbf{u}_1 = 0
$$

$$
\mathbf{Su}_1 = \lambda_1\mathbf{u}_1
$$

- $\mathbf{u_1}$ must be an eigenvector of $\mathbf{S}$
- multiply both sides with $\mathbf{u}_1^T$:

$$\mathbf{u}_1^T\mathbf{Su}_1 = \lambda_1\mathbf{u}_1^T\mathbf{u}_1 = \lambda_1
$$

- want to maximize variance, choose $\lambda_1$ as highest eigenvalue
- $\mathbf{u}_1$ is eigenvector with highest eigenvalue of $\mathbf{S}$, called ***first principal component*** of the data set

Algorithm:
1. Evaluate sample mean $\bar{\mathbf{x}}$ and covariance $\mathbf{S}$
2. Find $M$ eigenvectors of $\mathbf{S}$ containing $M$ largest eigenvalues $\{\lambda_1, \lambda_2,\dots,\lambda_M\}$
3. Project data onto subspace using:$$\mathbf{y} = \mathbf{U}^T\mathbf{x}$$$$\mathbf{U} = [\mathbf{u}_1,\mathbf{u}_2,\dots,\mathbf{u}_M]$$
 	- U is a matrix with eigenvectors as columns

## Minimum Error Formulation
Start with basis whose vectors satisfy:

$$
\mathbf{u}_i^T\mathbf{u}_j=\delta_{ij} = \begin{cases} 1 \quad\text{if } i=j \\ 0 \quad \text{otherwise} \end{cases}
$$

Rewrite each data point as:

$$
\mathbf{x}_n = \sum_{i=1}^D\alpha_{ni}\mathbf{u}_i
$$

- $\alpha_{ni}$ is measure of how strong each $\mathbf{u}_i$ is in data
	- represents coordinates of new data points
- represent data point $[x_1,x_2,\dots,x_D]^T_n$ using new coordinates $[\alpha_1,\alpha_2,\dots,\alpha_D]^T_n$
- Orthonormality gives $\alpha_{nj} = \mathbf{x}_n^T\mathbf{u}_j$ :

$$
\mathbf{x}_n = \sum_{i=1}^D(\mathbf{x}_n^T\mathbf{u}_i)\mathbf{u_i}
$$

Approximate $\mathbf{x}_n$:

$$
\tilde{\mathbf{x}}_n = \sum_{i=1}^Mz_{ni}\mathbf{u}_i +\sum_{i=M+1}^Db_i\mathbf{u}_i
$$

Choose $\mathbf{u}_i, z_{ni}$, and  $b_i$ to minimize difference between $\tilde{\mathbf{x}}_n$ and $\mathbf{x}_n$:

$$
J = \frac{1}{N}\sum_{n=1}^N||\mathbf{x}_n-\tilde{\mathbf{x}}_n||^2
$$

- Differentiating wrt $z_{ni}$ and $b_i$, setting to zero yields:

$$
z_{nj} = \mathbf{x}_n^T\mathbf{u}_j\qquad j = 1, 2, \dots, M
$$

$$
b_j = \tilde{\mathbf{x}}^T\mathbf{u}_j\qquad j = M+1,\dots, D
$$

Displacement vector lies in space orthogonal to principal subspace:

$$
\mathbf{x}_n-\tilde{\mathbf{x}}_n = \sum_{i=M+1}^D[(\mathbf{x_n}-\tilde{\mathbf{x}})^T\mathbf{u}_i]\mathbf{u_i}
$$

Sub into distortion measure $J$:

$$
\begin{align}J &= \frac{1}{N}\sum_{n=1}^N\bigg|\bigg|\sum_{i=M+1}^D[(\mathbf{x_n}-\tilde{\mathbf{x}})^T\mathbf{u}_i]\mathbf{u_i}\bigg|\bigg|^2\\&=\frac{1}{N}\sum_{n=1}^N\sum_{i=M+1}^D(\mathbf{x}_n^T\mathbf{u}_i-\tilde{\mathbf{x}}^T\mathbf{u}_i)^2
\\&=\sum_{i=M+1}^D\mathbf{u}_i^T\mathbf{Su}_i\end{align}
$$

To minimize:

$$
\mathbf{Su}_i = \lambda_1\mathbf{u}_i
$$

$$
J = \sum_{i=M+1}^D\lambda_i
$$

Distortion is represented in eigenvalues of dimensions > $M+1$

# Probabilistic PCA
Introduce random variables
1. Define random variable ***z*** in lower dimension with Guassian distribution
$$
p(\mathbf{z}) = \mathcal{N}(\mathbf{z}|0,\mathbf{I})
$$

2. Observed random variable ***x*** has a conditional distribution given by:
$$
p(\mathbf{x|z}) = \mathcal{N}(\mathbf{x}|\mathbf{Wz}+\boldsymbol{\mu}, \sigma^2\mathbf{I})$$where $$\mathbf{x} = \mathbf{Wz}+\boldsymbol{\mu}+\boldsymbol{\epsilon},\quad\boldsymbol{\epsilon}~\mathcal{N}(\mathbf{z}|0,\sigma^2\mathbf{I})
$$

4. Marginal distribution of data:

$$
p(\mathbf{x}) = \int p(\mathbf{x|z})p(\mathbf{z})d\mathbf{z}=\mathcal{N}(\mathbf{x}|\boldsymbol{\mu},\mathbf{C})
$$

where 
$$
\mathbf{C} = \mathbf{W}\mathbf{W}^T+\sigma^2\mathbf{I}
$$

5. Posterior distribution is:

$$
p(\mathbf{z|x})=\mathcal{N}(\mathbf{z}|\mathbf{M}^{-1}\mathbf{W}^T(\mathbf{x}-\boldsymbol{\mu}),\sigma^2\mathbf{M})
$$

Estimate parameters
- $\boldsymbol{\mu}_{ML}=\bar{\boldsymbol{x}}$
	- sample mean
- $\mathbf{W}_{ML} = \mathbf{U}_M(\mathbf{L}_M-\sigma^2\mathbf{I})^{\frac{1}{2}}\mathbf{R}$
	- $\mathbf{U}_M$ - eigenvector matrix
	- $\mathbf{L}_M$ - matrix of eigenvalues along diagonal
	- $\mathbf{R}$ - arbitrary rotation matrix
- $\sigma^2_{ML} = \frac{1}{D-M}\sum_{i=M+1}^D\lambda{i}$
	- average of eigenvalues we don't use

Can use [[Expectation Maximization (EM) Algorithm|EM Algorithm]]
- computational advantages in high dimensions
- can handle missing data
- required for factor analysis

## Factor Analysis
Very similar to probabilistic PCA, just the conditional distribution is different:
$$
p(\mathbf{x|z} = \mathcal{N}(\mathbf{x|Wz}+\boldsymbol{\mu},\boldsymbol{\Psi})
$$

where

$$
\mathbf{x}= \mathbf{Wz}+\boldsymbol{\mu}+\boldsymbol{\epsilon}\quad \boldsymbol{\epsilon}~\mathcal{N}(\mathbf{z}|0,\boldsymbol{\Psi})
$$

- ***W*** - factor loading matrix, explains covariance between observed variables
- ***&Psi;*** - uniqueness, independent noise variances for each observed variable