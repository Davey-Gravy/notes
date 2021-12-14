# Frank-Wolfe Algorithm
Based on first-order Taylor series expansion around current trial solution
1. Evaluate partial derivatives
$$
c_j = \frac{\partial f}{\partial x_j} \quad \text{at } \mathbf{x} = \mathbf{x}^{k-1}
$$
2. Formulate LP problem using partial derivatives as objjective function coefficients
$$
\begin{alignat}{3}
	\text{max} \quad &&& \mathrlap{g(\mathbf{x}) = \sum_{j=1}^nc_jx_j}\\
	\text{s.t.} \quad &&&& \mathbf{Ax} &\leq b\\
					  &&&& \mathbf{x} &\geq 0
\end{alignat}
$$

Optimal solution called $\mathbf{x}_{LP}^{(k)}$

3. Introduce variable $t(0 \leq t \leq 1)$, use:
$$
\mathbf{x} = \mathbf{x}^{(k-1)}+t\big(\mathbf{x}_{LP}^{(k)}-\mathbf{x}^{(k-1)}\big)
$$

Plug $\mathbf{x}$ into original objective function $f{\mathbf{x}}$, differentiate wrt $t$, set equal to zero
