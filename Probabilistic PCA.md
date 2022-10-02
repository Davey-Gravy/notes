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