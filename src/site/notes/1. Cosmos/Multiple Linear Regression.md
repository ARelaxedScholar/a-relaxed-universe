---
{"dg-publish":true,"permalink":"/1-cosmos/multiple-linear-regression/"}
---

202405181928
Status: #idea
Tags: [[Regression Analysis\|Regression Analysis]]
# Multiple Linear Regression
This is what we do when we have more than one regressor variables, more than one independent variables.
So
$$
y_i = \beta_0 + \beta_1 x_{i,1}+ \beta_2 x_{i, 2}+\dots\beta_n x_{i,k}
$$
This is a linear relationship with $k$ independent variables.

Technically you could do [[1. Cosmos/The Method Of Least Squares\|The Method Of Least Squares]] by hand and do differentiation for 2 regressor, 3 regressors, etc. 

But that'd be dumb, painful and slow. So instead we generalize it by writing everything in matrix form.

## Assumptions
$\epsilon_i$ is distributed according to $N(0, \sigma^2)$

## Notation
The above format while clear, is unwieldy and long.
We can instead write everything as matrices and store all of that same information in matrix format.

$$
\begin {align}
\boldsymbol Y &= (y_1, y_2, \dots, y_k)^T \\
\boldsymbol \beta &= (\beta_1, \beta_2, \dots, \beta_k)^T\\
\boldsymbol \varepsilon &= (\varepsilon_1, \varepsilon_2, \dots, \varepsilon_k)^T \\
\boldsymbol X &= \begin{pmatrix} x_{11} & x_{12} & \dots & x_{ik} \\ 
                                 x_{21} & x_{22} & \ddots & \vdots\\ 
                                 \vdots& & \ddots  & \vdots \\
                                 x_{n1} & x_{n2} & \dots &x_{nk}  \end{pmatrix}
\end {align} \text{, this is a n } \times \text{k matrix.}
$$

With all of those matrices defined I can write the regression for an arbitrary number of regressors:
$$
\boldsymbol Y = \boldsymbol \beta \boldsymbol X + \boldsymbol \varepsilon
$$

[[1. Cosmos/The Method Of Least Squares\|The Method Of Least Squares]]

[[1. Cosmos/Hypothesis Testing in Multiple Linear Regression\|Hypothesis Testing in Multiple Linear Regression]]

## References
[[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]]