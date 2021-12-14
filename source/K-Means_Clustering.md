# K-Means Clustering
- Exemplar - Old Faithful eruptions
	- correlation -> duration of eruption and time between eruptions
- Goal -> represent data in K clusters
	- each cluster has prototype $\mu_k$ -> representative data point
- [[Expectation Maximization (EM) Algorithm]] Algorithm:
	- Initialize prototypes (guess)
	- E-step -> assign each data point to a cluster based on a metric between data point and prototype (Euclidean distance)
	- M-step -> update prototype as cluster mean, based on E-step
	- Stopping criteria (number of steps, reassignment rate below threshold, cost function, etc.)
- Normalize data
## Math
- define *responsibilities*: $r_{nk} \in {0, 1}$ so that $\sum_k r_{nk} = 1$
	- Example: 5 data points and 3 clusters
	$$\textbf{\textit{R}} = (r_{nk}) = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 0 & 0 \end{bmatrix}$$
	- column -> cluster
	- row -> data point
- define cost function:
	$$J = \sum_{n=1}^N\sum_{k=1}^K r_{nk}\lvert\lvert\textbf{x}_n-\boldsymbol{\mu}_k\rvert\rvert^2$$
r<sub>nk</sub> - responsibilities
**x**<sub>n</sub> - data
&mu;<sub>k</sub> - prototypes
### E-Step
- minimize $J$ wrt $r_{nk}$
	- assigns each data point to nearest prototype
### M-Step
- minimize $J$ wrt $\mathbf{\mu}_k$
$$\mathbf{\mu}_k = \frac{\sum_n r_{nk}\mathbf{x}_n}{\sum_n r_{nk}}$$
- each prototype set to mean of data points in that cluster
- convergence guaranteed -> finite number of combinations of responsibilities

## Limitations
- forces hard assignment of data points to clusters
	- use "soft" probabilistic assignments instead
	- represented with [[Gaussian Mixture Models|Gaussian mixture model]]
- unclear to choose K