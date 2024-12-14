---
{"dg-publish":true,"permalink":"/1-cosmos/quadratic-discriminant-analysis-qda/","created":"2024-12-11T09:33:36.776-05:00","updated":"2024-12-13T09:22:38.453-05:00"}
---

202412110933
Status: #idea
Tags: [[1. Cosmos/Discriminant Analysis\|Discriminant Analysis]], [[1. Cosmos/Machine Learning\|Machine Learning]]
State: #nascient
# Quadratic Discriminant Analysis (QDA)

Well when doing [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]] we often make the simplifying assumption that the covariance of the distribution of $X$ is the same within each label class.

IT is convenient as it leads to nice cancellations and allow us to fit a model that is linear in the $X$, but what if the assumption of same covariance clearly doesn't hold?

Well if you have at least one covariance matrix which differs from the rest, you will need to approach cancellation differently and the result will be quadratic in the $X$ rather than linear.

As a result the decision boundary will now be curved rather than straight.

It is a powerful technique with one big cost, much more parameters.
In fact so much so that it becomes essentially unusable for datasets with a lot of predictors, in such cases [[1. Cosmos/Naive Bayes\|Naive Bayes]] which assumes that all the distributions are conditionally independent comes in clutch.

Indeed for $P$ predictors estimating a covariance matrix requires estimating $p(p+1)/2$ parameters (think of it as estimating the upper triangle of the covariance matrix and computing the area of that.)

Since we compute a new covariance matrix per class, this means $Kp(p+1)/2$ total parameters to estimate.

If we have 50 predictors, then that is $50(50+1)/2=2550/2=1275$ parameters PER COVARIANCE MATRIX!

That's a lot of parameters.

This is an example of the [[Bias-Variance Tradeoff\|Bias-Variance Tradeoff]], where the QDA model thanks to all its parameters is much more flexible than the [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]] model, but that is at the cost of higher variance.

As a result, we go for QDA if:
- Equal covariance assumption is clearly untenable
- We have a lots of data

It's better to use [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]] if:
- There are relatively few training examples

If even the normality assumption is too strontg then [[1. Cosmos/Naive Bayes\|Naive Bayes]]
A nice visualization:
![shot-2024-12-11_10-23-56.jpg](/img/user/3.%20Black%20Holes/Files/shot-2024-12-11_10-23-56.jpg)
## References
