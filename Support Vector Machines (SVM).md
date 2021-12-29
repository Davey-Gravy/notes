# Support Vector Machines (SVMs)


## Linear Classification/Regression

$$
y(x)=\mathbf{w}^T\phi(\mathbf{x})+b
$$

![[svm.png]]

Given a dataset of $n$ points $\{\mathbf{x}_n,t_n\},\: t_n\in\{-1,1\}$ we want to find the maximum-margin hyperplane that separates the points $\mathbf{x}_i$ that have $t_i=1$ from those with $t_i=-1$

Absolute distance of a point to the decision boundary is:

$$
\frac{t_ny(\mathbf{x}_n)}{||\mathbf{w}||}=\frac{t_n(\mathbf{w}^T\phi(\mathbf{x}_n)+b)}{||\mathbf{w}||}
$$

then the ***margin*** is defined as the minimum distance from the decision boundary to the training point:

$$
\min_n\frac{t_n(\mathbf{w}^T\phi(\mathbf{x}_n)+b)}{||\mathbf{w}||}
$$

The optimization problem is then:

$$
\arg\max_{\mathbf{w},b}\left\{\frac{1}{||\mathbf{w}||}\min_nt_n(\mathbf{w}^T\phi(\mathbf{x}_n)+b)\right\}
$$

This is difficult to solve, $\mathbf{w}$ and $b$ are scaled so that the distance to the margin is equal to one, since this doesn't change the relative distances between points:

$$
\min_nt_ny(\mathbf{x}_n)=\min_nt_n(\mathbf{w}^T\phi(\mathbf{x})+b)=1
$$

The optimization problem is then simplified to:

$$
\arg\max_{\mathbf{w},b}\left\{\frac{1}{||\mathbf{w}||}\cancelto{1}{\min_nt_n(\mathbf{w}^T\phi(\mathbf{x}_n)+b)}\right\}=\arg\max_{\mathbf{w},b}\left\{\frac{1}{||\mathbf{w}||}\right\}
$$

constrained such that:

$$
t_n(\mathbf{w}^T\phi(\mathbf{x}_n)+b)\geq 1
$$

Notice that

$$
\arg\max_{\mathbf{w},b}\left\{\frac{1}{||\mathbf{w}||}\right\}=\arg\min_{\mathbf{w},b}||\mathbf{w}||^2
$$

then for ease of differentiation the canonical representation is:

$$
\boxed{\begin{aligned}\arg\min_{\mathbf{w},b} \quad&\frac{1}{2}||\mathbf{w}||^2\\\text{s.t.}\quad&t_n(\mathbf{w}^T\phi(\mathbf{x}_n)+b)\geq 1\end{aligned}}
$$

This will be computed using the dual representation