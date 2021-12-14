# Unsupervised Learning
Learning from data without target variables
## Discrete Latent Variables
Unsupervised learning for classification
- Clustering
	- Different kinds of clustering models
		- Centroid
		- Distribution
		- Connectivity (hierarchical)
		- Others
	- Assignment of data into clusters
		- Hard
			- data assigned to one specific cluster
		- Soft
			- exist in multiple clusters

[[K-Means Clustering]]
[[Gaussian Mixture Models]]
[[Expectation Maximization (EM) Algorithm]]

## Continuous Latent Variables
Unsupervised learning for regression
Look at variables that are not observed, but assumed to exist --> ***latent***
- assumed to exist in functions that generate data

Example: digit recognition
- observed raw data --> pixel values
- hidden latent data
	- scaling
	- rotation
	- translation

High dimensional feature space vs. lower dimensional manifold
- observed data --> high dimensional space
- latent data --> lower dimensional manifold

Most simple case:
- [[Principal Component Analysis]], both observed and latent variables assumed to be Gaussian
	- Probabilistic PCA --> factor analysis

Non-Gaussian assumption:
- Independent component analysis
- Neural network autoencoders

