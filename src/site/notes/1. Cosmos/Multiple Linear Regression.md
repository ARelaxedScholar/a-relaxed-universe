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
\boldsymbol \beta &= (\beta_0, \beta_1, \beta_2, \dots, \beta_k)^T\\
\boldsymbol \varepsilon &= (\varepsilon_1, \varepsilon_2, \dots, \varepsilon_k)^T \\
\boldsymbol X &= \begin{pmatrix} 1 & x_{11} & x_{12} & \dots & x_{ik} \\ 
                                 1& x_{21} & x_{22} & \ddots & \vdots\\ 
                                 \vdots& & \ddots  & \vdots \\
                                 1& x_{n1} & x_{n2} & \dots &x_{nk}  \end{pmatrix}
\end {align} \text{, this is a n } \times \text{k+1 matrix.}
$$

With all of those matrices defined I can write the regression for an arbitrary number of regressors:
$$
\boldsymbol Y =  \boldsymbol X \boldsymbol \beta+ \boldsymbol \varepsilon
$$

[[1. Cosmos/The Method Of Least Squares\|The Method Of Least Squares]]

[[1. Cosmos/Hypothesis Testing in Multiple Linear Regression\|Hypothesis Testing in Multiple Linear Regression]]

## Covariance
We define the covariance of some vector Y as:
$$
Cov(V) = E[(Y-E(Y))(Y-E(Y))^T] := \varSigma\
$$
The above is often referred to as the variance-covariance matrix.

From there it follows that:
$$
Cov(AY)=A\varSigma A^T
$$

## [[1. Cosmos/Multivariate Normal\|Multivariate Normal]]
We already know that in the univariate case, a random variable $X$ is said to be normally distributed if it's pdf is :
$$
f_X = \frac{1}{\sigma\sqrt{2\pi}}exp(\frac{-(x-\mu)^2}{\sigma^2})
$$

Therefore by analogy, we can easily define a pdf for a normal that would be distributed according to multiple variables as follows:
$$
f_{multivariate X} = \frac{\varSigma^{-\frac{1}{2}}}{(2\pi)^{\frac{n}{2}}}exp(-\frac{1}{2}(X-\mu)^T\varSigma(X-\mu))
$$
Where:
- $\mu$ is a vector $(\mu_1, \mu_2, \dots, \mu_n)^T$
- $\varSigma$ is the variance-covariance matrix
- $n$ is the  number of variables.

We say that such a random variable is:
$$
Y \sim N_n(\mu, \varSigma)
$$

## Relevant Theorem
![Pasted image 20240606145958.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240606145958.png)

This is directly analogous to how in the univariate case, the linear combination of normally distributed random variables is a normally distributed variable.


## Special Cases:
- One of the predictor variables is a qualitative variable
- One of the predictor has a quadratic (polynomial) relation with response variable
- The predictor variables have a linear relation with a **transformation** of Y, example $ln(Y) = \beta_0 + \beta_1 X_1 + \dots + \beta_n X_n$.
- There is some interaction effect between predictor variables represented as a prodcut fo the predictor variables.
 ![Pasted image 20240606154751.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240606154751.png)

## Hypothesis Testing
### Checking for Significance of Regression
It checks if there's a **linear** relationship between the response variable and **any** of the $X_i$. it is often referred to as the [[Global Test of Model Adequacy\|Global Test of Model Adequacy]].

[[1. Cosmos/Test on Significance of Model (Crucial to know, but in general we know that our model is significant.)\|Test on Significance of Model (Crucial to know, but in general we know that our model is significant.)]]

### Checking for Significance of Specific Parameters
Typically we know that the model is significant, simply from looking at the data. Or at least we're pretty sure of it. While it's typically a slam dunk, we still want to show it for completeness and safety.

But the issue is that the previous test only tells us that some $\beta_i$ is not $0$, it does not tell us anything about which specifically it is. Therefore, we're going to want to check individual parameters.

It is not scary, it's pretty much the same thing as the [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]] case. We know that $Y$ is distributed according to a [[1. Cosmos/Multivariate Normal\|Multivariate Normal]]. Since $Y$ is nothing more than a linear combination of the $\beta_i$'s it follows that they are all distributed according to a $N(\mu, \sigma^2)$, so by standardizing we get $N(0,1)$ and then we take a test.

Except we don't really ever have $\sigma^2$ so instead we use the $MSE$ and have to use a $t-$distribution with the suitable degrees of freedom.
[[1. Cosmos/Test On Individual Regression Coefficient (Assuming We know our Model Is Significant)\|Test On Individual Regression Coefficient (Assuming We know our Model Is Significant)]]


## References
[[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]]