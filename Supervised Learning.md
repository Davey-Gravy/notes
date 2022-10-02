# Background

Given ***training samples***,

$$
\{\mathbf{x}_n,t_n\}
$$

- $\mathbf{x}_n$ - training data
- $t_n$ - target values

$$
t_n = f(\mathbf{x}_n)
$$

find a good approximation to the desired function

$$
y(\mathbf{x})\approx f(\mathbf{x})
$$
Goal:
- Minimize ***generalization error***
	- probability of making an error on *unseen* data points
	- cross-validation

## Scenarios

Medical diagnosis

- $\mathbf{x}$ - set of symptoms of a patient
- $f(\mathbf{x})$ - their disease

Property evaluation

- $\mathbf{x}$ - sales information
- $f(\mathbf{x})$ - suggested price

Speech recognition

- $\mathbf{x}$ - recorded signal
- $f(\mathbf{x})$ - sentence in words

# When to Use?

- There is no human expert
- Humans can perform the task but can't explain how
- The desired function changes too frequently
- The application is user-specific

# Methods

- [[Decision Trees]]
- [[Linear Regression]]
- [[K-Nearest Neighbors (kNN)]]
- [[Support Vector Machines (SVM)]]
- [[Neural Networks]]