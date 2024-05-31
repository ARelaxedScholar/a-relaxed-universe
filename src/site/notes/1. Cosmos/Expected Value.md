---
{"dg-publish":true,"permalink":"/1-cosmos/expected-value/"}
---

202405031126
Status: #idea
Tags: [[Statistics\|Statistics]], [[Probability\|Probability]]
# Expected Value
## Elementary Probability
It is a weighted average of all the values that a [[1. Cosmos/Random Variable\|random variable]] under consideration can take. It is weighted to account for the it is computed as follows:
$$
EV = \sum P(X_i)\times X_i
$$
Where each probability is weighted by the actual value of its observation.

This value gives us on average, what would be the most likely value that $X$ would take.


## In MAT3172
$$
E(X) = \intop_{-\infty}^{\infty}x~dF(x)= \intop_{-\infty}^{\infty}xF'(x)~dx=\intop_{-\infty}^{\infty}xf(x)~dx \text{, if it exists}
$$
This definition makes use of what's called a [[1. Cosmos/Riemann-Stieltjes Integrals ~ Generalization of Riemann integrals\|Riemann-Stieltjes Integrals ~ Generalization of Riemann integrals]] where instead of differentiating directly with respect to $x$, we differentiate with respect to some non-decreasing function $\alpha$. Here we know by definition that a [[1. Cosmos/Cumulative Density Function\|Cumulative Density Function]] ($F(x$)) is always non-decreasing, therefore we can integrate with respect to it. 

Observe that the general form is the first equation, this form can be used for ANY cdf you toss at me, as in the worst case (if the cdf is not continuous) I can solve it by doing [[Integration by Parts\|integration by parts]], the latter two which are the equations we are typically given in [[1. Cosmos/Expected Value#Elementary Probability\|#Elementary Probability]] for continuous random variables. They are used when we are dealing with a [[1. Cosmos/Random Variable#Continuous Random Variables\|continuous random variable]] and therefore its [[1. Cosmos/Cumulative Density Function\|cumulative density function]] is continuous, most of the time the functions we deal with in such classes will be both continuous and differentiable. But this does not have to be the case.

We can update the definition of variance in a similar fashion: [[1. Cosmos/Variance#In MAT3172\|Variance#In MAT3172]]
## Properties
1. $E(\sum c_iX_i) = \sum c_i E(X_i)$
2. $X \leq Y \leq Z \implies E(X) \leq E(Y) \leq E(Z)$

I spent an ungodly amount of time explaining expected value in [[1. Cosmos/Probability Measure (Based on Expected Value)\|Probability Measure (Based on Expected Value)]] so you can check the details there (at least until I bring it here.)
## References
