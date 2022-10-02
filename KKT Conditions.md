***K***arush-***K***uhn-***T***ucker (KKT) Conditions
- Used to find optimal solution of a general nonlinear programming (NLP) problem
- Requires $f(x)$ to be concave and differentiable, $g_i(x)$ to be convex
1. $$\frac{\partial f}{\partial x_j} - \sum_{i=1}^m u_i\frac{\partial g}{\partial x_j} \leq 0$$
2.  $$x_j\bigg(\frac{\partial f}{\partial x_j} - \sum_{i=1}^m u_i\frac{\partial g}{\partial x_j}\bigg) = 0$$
3.  $$g_i(\textbf{x})-b_i \leq 0$$
4.  $$u_i[g_i(\textbf{x})-b_i] \leq 0$$
5.  $$x_j \geq 0$$
6.  $$u_i \geq 0$$

- $i$ - index of constraints
- $j$ - index of decision variables
- $m$ - number of constraints
- $n$ - number of decision variables
