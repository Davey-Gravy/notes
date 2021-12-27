# Under-Relaxation

Used to improve stability of iterative matrix solvers


## Generally

Fraction of the field variable from the previous iteration is used for the current iteration. Using pressure as an example:

$$
p = \alpha p_{new}+(1-\alpha)p_{old}
$$

## [[SIMPLE Algorithm]]
Intended for steady flows (no time derivative)

$$
\frac{\partial\boldsymbol{U}}{\partial t}=\frac{\boldsymbol{U}_p^{i+1}-\boldsymbol{U}_p^{i}}{\Delta t}
$$

- Time derivative terms are always on diagonal of matrices
	- As $\Delta t \rightarrow 0$, $\frac{\partial\boldsymbol{U}}{\partial t}$ grows larger --> improves diagonal dominance
		- improves stability

Since there is no time derivative in steady flows, ***under-relaxation*** is used to artificially improve diagonal dominance

Under-relaxation term $0<\alpha\leq1$ introduced to the equations:

$$
a_P\boldsymbol{U}_P+\sum_Na_N\boldsymbol{U}_N=R_P
$$

- $P$ - diagonal terms
- $N$ - off-diagonal terms

$$
\frac{1-\alpha}{\alpha}\boldsymbol a_p{U}_P+a_P\boldsymbol{U}_P+\sum_Na_N\boldsymbol{U}_N=R_P+\frac{1-\alpha}{\alpha}a_P\boldsymbol{U}^\text{old}_P
$$

$$
\Big(\frac{1-\alpha}{\alpha}+1\Big)a_P\boldsymbol{U}_P+\sum_Na_N\boldsymbol{U}_N=R_P+\frac{1-\alpha}{\alpha}a_P\boldsymbol{U}^\text{old}_P
$$

$$
\frac{1}{\alpha}a_P\boldsymbol{U}_P+\sum_Na_N\boldsymbol{U}_N=R_P+\frac{1-\alpha}{\alpha}a_P\boldsymbol{U}^\text{old}_P
$$

- diagonal term gets larger as $\alpha\rightarrow0$