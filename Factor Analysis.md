# Factor Analysis
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