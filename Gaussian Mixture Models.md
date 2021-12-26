# Gaussian Mixture Models
- soft assignment of data to clusters
	- probabilistic treatment to clustering
- each cluster represented by a Gaussian, mixed together with weighing coefficient

## 4 Operations
1. Calculate total likelihood *p(**x**)*
2. Draw sample from distribution ***x*** ~ *p(**x**)*
3. Assign a point to a cluster
4. Determine model parameters (EM algorithm)
	- Mixing coefficients
	- Prototypes (mean vectors)
	- Covariance matrices


### Calculate Total Likelihood
Likelihood of data point belonging to specific cluster:
$$p(\textbf{x}|\mathcal{C}_k) = \mathcal{N}(\textbf{x}|\boldsymbol{\mu}_k, \boldsymbol{\Sigma}_k)$$
Total likelihood:
$$p(\textbf{x}) = \sum_{k=1}^K\pi_k\mathcal{N}(\textbf{x}|\boldsymbol{\mu}_k, \boldsymbol{\Sigma}_k)$$

### Sampling from Gaussian Mixtures
Generate a single data point
1. Pick one of the components using probability *&pi;*<sub>k</sub>
2. Draw a sample from that component

### Assign Point to a Cluster
Labels -> latent (hidden) variables:
$$z_k \in \{0, 1\} \qquad \sum_{k=1}^K z_k = 1 \qquad \textbf{z} = \begin{bmatrix}z_1 \\ z_2 \\ \vdots \\ z_K \end{bmatrix}$$
K = number of clusters

Probability of element *z* given in terms of mixing coefficients:
$$p(z_k = 1)= \pi_k \quad \text{with} \quad 0\leq\pi_k\leq1,\quad\sum_{k=1}^K\pi_k = 1$$
Probability of vector ***z***:
$$p(\mathbf{z}) = \coprod_{k=1}^K\pi_k^{z_k} = \pi_1^0\pi_2^0\dots\pi_k^1\dots\pi_K^0 = \pi_k$$
- Only one element of ***z*** = 1

Conditional probability of ***x*** given value for latent variable ***z***:
$$p(\mathbf{x}|z_k = 1) = \mathcal{N}(\mathbf{x}|\boldsymbol{\mu}_k, \boldsymbol{\Sigma}_k)$$
Rewritten as:
$$p(\mathbf{x}|\mathbf{z} = \coprod_{k=1}^K\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}_k, \boldsymbol{\Sigma})k$$
Joint distribution:
$$p(\mathbf{x}, \mathbf{z}) = p(\mathbf{z})p(\mathbf{x}|\mathbf{z})$$
Marginal distribution:
$$p(\mathbf{x}) = \sum_\mathbf{z}p(\mathbf{z})p(\mathbf{x}|\mathbf{z}) = \sum_{k=1}^K\pi_k\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}_k, \boldsymbol{\Sigma}_k)$$

Conditional probability that data is in a cluster given the data point :
$$\gamma(z_k)=p(z_k= 1|\mathbf{x})=\frac{p(z_k=1)p(\mathbf{x}|z_k=1)}{\sum_{j=1}^K\pi_j\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}_j, \boldsymbol{\Sigma}_j)}=\frac{p(\mathbf{z})p(\mathbf{x}|\mathbf{z})}{p(\mathbf{x})}$$
Bayes' theorem

Assign each point a probability of being in a class

Can't use log maximum likelihood
- instead use expectation maximization (EM) algorithm