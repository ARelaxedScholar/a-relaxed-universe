---
{"dg-publish":true,"permalink":"/1-cosmos/simple-linear-regression/","created":"2024-08-31T23:47:13.585-04:00","updated":"2024-05-20T21:41:32.760-04:00"}
---

202405031405
Status: #idea
Tags: [[1. Cosmos/Regression\|Regression]]
# Simple Linear Regression
![Pasted image 20240503141031.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240503141031.png)
*The above represent the standard equation of a Simple Linear Regression. Since we typically don't know the exact Y, $\beta_0$ and $\beta_1$ we will typically write them with a ^ on them.*

For the purposes of SLE the parameters are the following:
Y : random variable (dependent variable, response)
X : fixed variable, the thing we control (independent variable, regressor, predictor)
$\beta_0$ and $\beta_1$: Fixed parameters (true value is unknown)
$\epsilon$: Random error term ([[1. Cosmos/Random Variable\|Random Variable]])
The data is arranged in pairs $(X_1, Y_1), (X_2, Y_2), \dots, (X_n, Y_n)$


While the term Linear Regression might lead you to assume that all regressions will have the form $y=mx+b$ we would also call linear a regression of the form $y=nx^2+mx+b$, while we have quadratic term, the parameters ($n,m,b$) are all raised to the $1$ **AND** the equation is written as a summation of the parameters with some coefficient. Also please be keenly aware that a line that fits neatly does not mean anything!

We could relate stock market prices in N.Y to the price of bananas in an offshore island, it does not mean anything and it would be silly to make any financial decisions based on that.

[[1. Cosmos/Assumptions of Simple Linear Regression\|Assumptions of Simple Linear Regression]]
[[1. Cosmos/The Method Of Least Squares\|The Method Of Least Squares]]
[[1. Cosmos/Goodness of Fit\|Goodness of Fit]]

## References
[Simple Linear Regression Intuitions by the Goat JBStats](https://www.youtube.com/watch?v=KsVBBJRb9TE&list=PLvxOuBpazmsND0vmkP1ECjTloiVz-pXla)
[Derivating the OLS coefficients Video 1](https://www.youtube.com/watch?v=jqoHefiIf9U)
[Derivating the OLS coefficiences Video 2](https://www.youtube.com/watch?v=jqoHefiIf9U)
[How To Show Unbiasedness of Estimators for m and b](https://www.youtube.com/watch?v=5tMMESxjDBg)

