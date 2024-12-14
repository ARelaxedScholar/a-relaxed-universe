---
{"dg-publish":true,"permalink":"/1-cosmos/multinomial-logistic-regression/","created":"2024-12-11T08:06:36.754-05:00","updated":"2024-12-13T09:09:17.293-05:00"}
---

202412110806
Status: #idea
Tags: [[1. Cosmos/Logistic Regression\|Logistic Regression]], [[1. Cosmos/Linear Methods for Classification\|Linear Methods for Classification]]
State: #nascient
# Multinomial Logistic Regression

What if you wanted to use [[1. Cosmos/Logistic Regression\|Logistic Regression]] on a classification problem with more than 2 labels?

You use multinomial logistic regression.
This a generalization of what we already did in the single variable case where $p(x)=\frac{e^{X^T\beta}}{1+e^{X^T\beta}}$ and the complement or baseline ends up being $1-p(x)=\frac{1}{1+e^{X^T\beta}}$.

Similarly for $K$ levels, we pick any one of them (it doesn't matter in the end) to be a baseline, this means that we do not compute regression parameters for it.

As a result, for any $k\in \{1,\dots, K\}\setminus \{K_{chosen}\}$ 
we have
$$
P(Y=k| X=x)=\frac{e^{\beta_{k0}+\beta_{k1}x_1+\dots+\beta_{kp}x_p}}{1+\sum_{k\ne K_{chosen}}{\beta_{i0}+\beta_{i1}x_1+\dots+\beta_{ip}x_p}}
$$
and for the baseline
$$
P(Y=K_{chosen}| X=x)=\frac{1}{1+\sum_{k\ne K_{chosen}}{\beta_{i0}+\beta_{i1}x_1+\dots+\beta_{ip}x_p}}
$$

We'd then assign the label with the highest probability.

We can then show in a fashion identical to the binary case that the log-odds of any $k$ with the baseline $K_{chosen}$ is linear in the $X$, so we still have linear decision model. 

For that reason, it doesn't strictly matter which level we pick as the baseline, so if we use software it will generally pick it as either the first level or the last level automatically, or if we want to set a baseline ourselves, we can generally do so using the provided method in whatever framework we use.

While no matter which level we pick the decisions made by the model will be identical, being aware of the baseline is extremely important as the log-odds and the meaning of a change in one direction or another relates back to that baseline.

For that reason, at times it might make sense to pick a different baseline than the automatically picked one if we want to change the comparison reference.

## Softmax Coding
The way we did it above is an extension of the classical logistic regression model, but those familiar with machine learning and deep learning are likely familiar with another notation:
$$
P(Y=k|X=x)=\frac{e^{\beta_{k0}+\beta_{k1}x_1+\dots+\beta_{kp}x_p}}{\sum_{k=1}^{K}{\beta_{i0}+\beta_{i1}x_1+\dots+\beta_{ip}x_p}}
$$

Here we do not pick a baseline and simply fit parameters for the whole slew, we then need to estimate the $K$ set of coefficients rather than $K-1$ sets. It is extensively done in [[1. Cosmos/Machine Learning\|Machine Learning]] and [[Deep Learning\|Deep Learning]], because this method is efficient computationally as it aligns better with the gradient-based optimization frameworks that are often used.

In this configuration we can take the log-odds between any two ratios $k, k'$ as:
$$
ln(\frac{P(Y=k|X=x)}{P(Y=k'|X=x)})=(\beta_{k0}-\beta_{k'0})+(\beta_{k1}-\beta_{k'1})x_1+\dots+(\beta_{kn}-\beta_{k'n})x_n
$$


## Pros & Cons
### Pros
- Natural generalization of [[1. Cosmos/Logistic Regression\|Logistic Regression]]
- Calibrated probability regressor for each class (all sum to $1$)
### Cons
- Can be unstable where the classes are well separable (surprisingly)
- Other issues that I forget at this point

For these reasons, the replacement if we want to keep the decision boundary linear while still being to retrieve the probability if we need it is often the [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]].
## References
