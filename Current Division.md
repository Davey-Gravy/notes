# Overview

Isolates the amount of current through a subset of a parallel circuit

$$
i_k=\frac{R_\text{parallel}}{R_k}\,=\frac{\Pi_k}{\sum_{i=1}^n\Pi_i}
$$

Where $\Pi_k$ is the product of all resistances excluding $R_k$

# Example

> Formulate current division given resistors $R_1,\,R_2,\,R_3$ and current input $i$:
> > $$R_\text{parallel}=\left(\frac{1}{R_1}+\frac{1}{R_2}+\frac{1}{R_3}\right)^{-1}$$
> > $$V=R_\text{parallel}\,i$$
> > $$\boxed{\begin{align}i_1&=\frac{V}{R_1}=\frac{R_\text{parallel}}{R_1}\,i\\i_2&=\frac{V}{R_2}=\frac{R_\text{parallel}}{R_2}\,i\\i_3&=\frac{V}{R_3}=\frac{R_\text{parallel}}{R_3}\,i\end{align}}$$