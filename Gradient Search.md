# Gradient Search
Similar to gradient descent, instead of marching downward to minimize error, climb upward to maximize objective function

1. Initialize with trial solution $x'$, select $\epsilon$
2. Express $f(\mathbf{x}' + t\nabla f(\mathbf{x}'))$ as a function of $t$ by setting 

$$
x_j = x_j' + t\bigg(\frac{\partial f}{\partial x_j}\bigg)_{\textbf{x}=\textbf{x}'}
$$

and substituting into $f(\mathbf{x})$.

3. Use search procedure to find $t=t^*$ that maximizes $f(\mathbf{x}' + t\nabla f(\mathbf{x}'))$
4. Reset $\mathbf{x}' + t^*\nabla f(\mathbf{x}')$
5. Check stopping rule, evaluate $\nabla f(\textbf{x}')$ at $\textbf{x} = \textbf{x}'$, check if

$$
\bigg|\frac{\partial f}{\partial x_j}\bigg|\leq \epsilon
$$