# Method of Undetermined Coefficients

Used when the right hand side of a [[Ordinary Differential Equations (ODEs)#Non-homogeneous|non-homogeneous ODE]] is a sum or product of simple polynomial, exponential, and trigonometric functions.

A guess is made about the form of the solution, which is then substituted in and coefficients are selected to satisfy the equation.

| $f(t)$                     | Prototype                  |
| -------------------------- | -------------------------- |
| $e^{at}$                   | $Ae^{at}$                  |
| $\cos(at)$                 | $A\cos(at)+B\sin(at)$      |
| $\sin(at)$                 | $A\cos(at)+B\sin(at)$      |
| $at^n+bt^{n-1}+\dots+mt+n$ | $At^n+Bt^{n-1}+\dots+Mt+N$ | 

Products of functions can be represented by products of their prototypes, for example:

| $f(t)$           | Prototype                         |
| ---------------- | --------------------------------- |
| $e^{at}\sin(bt)$ | $Ae^{at}\cos(bt)+Be^{at}\sin(bt)$ |
| $t^2e^{at}$      | $At^2e^{at}+Bte^{at}+Ce^{at}$             |

