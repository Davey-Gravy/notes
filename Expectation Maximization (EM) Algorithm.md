- More general, used for [[Gaussian Mixture Models]] in this note
	- assume parameters known to find responsibilities
		- Differentiate the likelihood function wrt to means, set to zero
			- Likelihood function:
			$$\ln p(\mathbf{X}|\boldsymbol{\pi}, \boldsymbol{\mu}, \boldsymbol{\Sigma})=\sum_{n=1}^N\ln\bigg\{\sum_{k=1}^K\pi_k\mathcal{N}(\mathbf{x}_n|\boldsymbol{\mu}_k, \boldsymbol{\Sigma}_k\bigg\}$$
			- Differentiated, set to zero:
			$$\begin{align}
			0 &= \sum_{n=1}^N\frac{\pi_k\mathcal{N}(\mathbf{x}_n|\boldsymbol{\mu}_k, \boldsymbol{\Sigma}_k}{\sum_{j=1}^K\pi_j\mathcal{N}(\mathbf{x}_n|\boldsymbol{\mu}_j,\boldsymbol{\Sigma}_j)}\boldsymbol{\Sigma}_k^{-1}(\mathbf{x}_n-\boldsymbol{\mu}_k\\
			&= \sum_{n=1}^N\gamma(z_{nk})\boldsymbol{\Sigma}_k^{-1}(\mathbf{x}_n-\boldsymbol{\mu}_k)\end{align}$$
		- assume we can calculate $\gamma(z_{nk})$
			- can obtain mixture means:
			$$\boldsymbol{\mu}_k = \frac{1}{N_k}\sum_{n=1}^N\gamma(z_{nk})\mathbf{x}_n$$
			- effective number of points for each component *N<sub>k</sub>*
			$$N_k = \sum_{n=1}^N\gamma(z_{nk})$$
		- Estimating covariance 
			$$\boldsymbol{\Sigma}_k = \frac{1}{N_k}\sum_{n=1}^N\gamma(z_{nk}(\mathbf{x_n}-\boldsymbol{\mu}_k)(\mathbf{x_n}-\boldsymbol{\mu}_k)^T$$
		- mixing coefficients
			$$\pi_k = \frac{N_k}{N}$$
	- iteration
		- make initial guess of parameters
		- alternate between:
			- E-step: evaluate responsibilities $\gamma_{nk}$
			- M-step: update parameters using results
			