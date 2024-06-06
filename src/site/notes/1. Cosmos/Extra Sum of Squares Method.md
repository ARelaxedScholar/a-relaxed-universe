---
{"dg-publish":true,"permalink":"/1-cosmos/extra-sum-of-squares-method/"}
---

202405182101
Status: #idea
Tags: [[1. Cosmos/Hypothesis Testing in Multiple Linear Regression\|Hypothesis Testing in Multiple Linear Regression]]
# Extra Sum of Squares Method
This is a similar idea to what we do when we are [[1. Cosmos/Test on Significance of Model (Crucial to know, but in general we know that our model is significant.)\|checking significance of model]] except that instead of checking the full set of regressors at once with [[1. Cosmos/Analysis of Variance (ANOVA)\|Analysis of Variance (ANOVA)]], we select a subset of coefficients that we suspect might be useless and test them.

## Intuition
When I have the intuition that a subset of regressors are useless, I am essentially intuiting that the smaller model called [[Restricted Model\|Restricted Model]] does not have significantly less predictive power than the model with all the regressors called [[Full Model\|Full Model]].

In other terms, we say that we can with impunity remove those parameters and keep the power the same. This is not usually expected since in general as the number of regressors increase, the predictive power of our model increases. This can be stated as "as the number of regressors increase, the $SSE$ of our model decreases" OR "as the number of regressors increase, the $SSReg$ of our model increases".

So our null hypothesis will essentially say that the restricted model is enough, in other terms that $Y = X\beta_{restricted}$, and the alternative hypothesis will be that $Y = X\beta_{full}$.

From there we proceed.
## Method
The idea is to split our $\beta$ vector into two parts, the part that we think is useful and that will encompass the restricted model, and the rest that will be added on top of the supposed useful part. You do not have to change the dimensions of the $\beta$ vector (even though you could, if you adjust everything else to match), all you need to do is to set those parameters to $0$. Why? Because we're doing linear combinations and setting those coefficients to 0 will nullify all the other terms.

In so doing, we effectively have two models to compare. And from these two models we can compute a $SSReg$ that gives us the amount of variation around the mean that is explained by the model. 

So we are comparing these models through their respective $SSReg$ which we observe is distributed according to a $\chi^2$ distribution and which are independent (foreshadowing.)

By taking the difference between the $SSReg$ of the full model and the restricted model, we can numerically capture how much variance around the mean is explained by adding those new parameters. In other terms we can quantify the increase in explanatory power of our model. 

This difference will have $(k-1)-(k-1-r)$ or in other terms $r$ degrees of freedom.

Note that the full model has $SSReg$ has $n-k$ degrees of freedom as we are used to.

We now want to see how significant of a difference the added parameters make.

As we often do in statistic, whenever we want to compare two things, and that those two things happen to be independently distributed according to a $\chi^2$, we can divide the two things (making sure to divide by the respective degree of freedoms beforehand) to obtain what's called a $F$-statistics, which will have the degree of freedoms of the numerator along one dimension, and the degree of freedom of the denominator across the other.

If this F statistic is bigger than the appropriate $F_\alpha$ we will conclude that our idea that parameters were useless is false, and conclude that the full model is better in a statistically significant fashion. Else, we fail to reject the null hypothesis.
## Video Screenshots
![Pasted image 20240518213652.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518213652.png)

![Pasted image 20240518211159.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518211159.png)