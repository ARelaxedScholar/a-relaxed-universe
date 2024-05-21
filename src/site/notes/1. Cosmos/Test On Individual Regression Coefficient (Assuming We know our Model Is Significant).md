---
{"dg-publish":true,"permalink":"/1-cosmos/test-on-individual-regression-coefficient-assuming-we-know-our-model-is-significant/"}
---

202405202141
Status: #idea
Tags: [[Regression Analysis\|Regression Analysis]]
# Test On Individual Regression Coefficient (Assuming We know our Model Is Significant)

We test the hypothesis that 
$H_0: \beta_j = 0$
$H_1: \beta_j \ne 0$
We know that our $\hat \beta$ is distributed according to a normal distribution with mean $\beta$ since it is a [[BLUE Estimator\|BLUE Estimator]] and that it has variance $\sigma^2(x^Tx)^{-1}$/

By this logic we know that all the elements in the $\hat \beta$ vector have to be normally distributed as well. So like in [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]] we can simply use z-tests and t-tests to find our answer.

Except we lack the variance for a specific $\beta_j$ or do we? We need to observe that the variance of $\hat \beta$ is $\sigma^2$ $\times$ $(x^Tx)^{-1}$ which is really just the covariance matrix of all $\beta_i$. To find the variance for a specific $\beta_j$ we simply index this matrix at the diagonal such that the variance of $\beta_j$ is $\text{covariance matrix @ index (j,j)}$ which is $(x^Tx)^{-1}_{jj}$.

From there we can easily compute our statistic, keep in mind that in the image below we're checking for significance of the slope so we are assuming $\beta_j$ is $0$. If the test was say $\beta_j=1$ then we'd subtract 1 from $\hat \beta_j$.

As usual we do not have $\sigma^2$ in pretty much all the cases, so we use $MSE$ instead which is computed by as follows $\frac{SSE}{n-k}$ where $k$ is the number of parameters. Look at [[1. Cosmos/The Method Of Least Squares in Multiple Linear Regression\|The Method Of Least Squares in Multiple Linear Regression]] for the specific formulas.

Obviously, the $t$ distribution it follows will have $n-k$ number of parameters.

*Accustom yourself with the following image*
![Pasted image 20240518205416.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518205416.png)

## References