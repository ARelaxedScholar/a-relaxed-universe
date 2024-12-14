---
{"dg-publish":true,"permalink":"/1-cosmos/assumptions-of-simple-linear-regression/","created":"2024-08-31T23:47:13.678-04:00","updated":"2024-12-13T09:27:50.840-05:00"}
---

 
sa 202405031131
Status: #idea
Tags: [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]]
# Assumptions of Simple Linear Regression
![Pasted image 20240503112122.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240503112122.png)
This image implies that $\epsilon$ is normally distributed with mean ($\mu$) of 0 and variance of $\sigma^2$. By virtue of that, we have the confidence that if we take a big enough sample of observations, since the error of our prediction on all these observations will be distributed according to $N(0, \sigma^2)$, the errors will cancel. In other words, the linear regression is an [[Unbiased Model\|Unbiased Model]] some observations will overshoot and others will undershoot such that when collated we get 0. For rigour a third property $Cov(\epsilon_i, \epsilon_j) =0$ for all different $i,j$ but that just means that the error terms are uncorrelated which we already stated.

When the variance of all random variables is the same we say that the random variables are [[Homoscedastic\|Homoscedastic]].

Thanks to that the following two results follow:
![Pasted image 20240503140910.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240503140910.png)
Equivalent images, but the top one is more precise, we write the first one because we assume that the $X$ vector is fixed. The $\beta$ parameters and $X$ vector being fixed is the reason this equality is true $E(\beta_0+ \beta_1 X_i + \epsilon_i) = \beta_0 + \beta_1 X_i + E(\epsilon_i)$. Since the $\beta$ parameters and the $X$ are fixed, they act as constants and their expectation is themselves.

![Pasted image 20240503112443.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240503112443.png)

The [[1. Cosmos/Expected Value\|Expected Value]] of y will be exactly the regression line $\beta_0+\beta_1X$ and the variance of $y$ will coincide with the variance of the terms. Please try to convince yourself of that.

The variance of $Y$ is $\sigma^2$ due to how we compute $Y$. The error is normally distributed and the expected value of Y (or true Mean of Y given the observations) is given to be the $\beta_0+\beta_1 X$ line without the error. The only thing that can make the mean vary is the error, which is $\epsilon$ which recall has mean $0$ and variance $\sigma^2$. What does that mean? That means epsilon is normally distributed, and $Y$ varying because of epsilon is normally distributed as well. While the mean is going to be $Y$, the variance is going to be $\sigma^2$ due to how the random error terms are distributed.

## The Formulas
To estimate $\beta_1$ we will use $t$-table to do confidence intervals and the following formulas. The degree of freedom of this $t$ will be $n-1$ ($n$ is the sample size), look at the calculation of the standard error to understand why. If we do inference, we will typically do it on the slope since it is the variable that captures how $Y$ (the response variable) changes with respect to $X$ (the predictor.) In the general the test will be of the null hypothesis that the slope is 0. In other terms there is no relation between the two. Check [[1. Cosmos/Hypothesis Test\|Hypothesis Test]] for a reminder.
[[1. Cosmos/Formulas from JBStats\|Formulas from JBStats]]
[[1. Cosmos/Formulas from Notes\|Formulas from Notes]]

## Inference in Simple Linear Regression
We observe that both estimators are distributed according to a t distribution with n-2 degrees of freedom. This is exceedingly good for us since it means that we can easily find the t-statistics that we need through a process called standardization which consists of substracting the mean from the datum, and dividing by the standard deviation to bring back to a standard normal distribution:
$$
t_{stat} = \frac{x-\mu}{\sigma}
$$
But! When we're doing simple linear regression, the $\sigma$ we have refers to the $\epsilon$ and transitively the $Y$ itself, not the slope and intercept parameters. Therefore we must derive the formula that relate that $\sigma$ to our slope and intercept. Likewise we do not have $\mu$ almost all the time (not really relevant here since this is mostly used for [[1. Cosmos/Hypothesis Test\|Hypothesis Test]].)

So the derivation gives us that the standard deviation (also called Standard Error) as it relates to the slope is given by $\sqrt{\frac{\sigma^2}{SS_{xx}}}$ which is for lack of better term the standard deviation of the slope. Therefore for any inference that needs this "standard deviation" we will use this standard error instead.

Likewise, the formula for the standard error of $\beta_0$ is $\sqrt{\sigma^2(\frac{1}{n}+\frac{\bar X^2}{SS_{xx}})}$. This is the "standard deviation" of the y-intercept. Big air quotes because since we have one of each, standard deviation is a weird term.

Anyhow, now that we have those we can do confidence intervals and hypothesis tests, right? Not quite! While it is true that we're almost there, in real life we pretty much never have $\sigma^2$ as well. Which is why we need an unbiased estimator for it, this estimator happens to be the $MSE$ which is computed as $\frac{SSE}{n-2}$ which is equivalent to $\frac{SS_{yy}-\beta_1 SS_{xy}}{n-2}$ which is also equivalent to $\frac{SS_{yy}-\frac{SS_{xy}^2}{Ss_{xx}}}{n-2}$ . Point is, replace $\sigma^2$ by $MSE$ and we are gucci.  
## References
[[1. Cosmos/Properties of Least Square Estimators in SLR\|Properties of Least Square Estimators in SLR]]
[[MAT3375(X) ~ Regression Analysis#Lecture 1\|MAT3375(X) ~ Regression Analysis#Lecture 1]]
[Example of Inference on the Slope](https://www.youtube.com/watch?v=nk_0RcHI-vo&list=PLvxOuBpazmsND0vmkP1ECjTloiVz-pXla&index=7)
[Example of Simple Linear Regression](https://www.youtube.com/watch?v=xIDjj6ZyFuw&list=PLvxOuBpazmsND0vmkP1ECjTloiVz-pXla&index=8)