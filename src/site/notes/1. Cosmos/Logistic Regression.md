---
{"dg-publish":true,"permalink":"/1-cosmos/logistic-regression/","created":"2025-01-22T11:17:14.068-05:00","updated":"2024-12-13T09:06:35.642-05:00"}
---

202412091014
Status: #idea
Tags: [[1. Cosmos/Classification\|Classification]], [[Discriminative Models\|Discriminative Models]]
State: #nascient
# Logistic Regression

One of the big two of [[1. Cosmos/Linear Methods for Classification\|Linear Methods for Classification]] and also just a classic classification method. That is [[1. Cosmos/Logistic Regression\|Logistic Regression]] and [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]].

It arises from the desire to fit a model that can predict the posterior probability given some vector $x$ $P(G=k|X=x)$  similarly to what we'd do with [[1. Cosmos/Linear Regression\|linear regression]] but while constraining to what make probabilities probabilities, that is:
- The probability of each class sums to $1$
- Every individual probability is between $0$ and $1$ inclusive.

It takes the form:
$$
p(X)=\frac{e^{\beta_0+\beta_1X}}{1+e^{\beta_0+\beta_1X}}
$$
Where as we can see we are using $exp(\text{linear model})$ on both the top and bottom, and then add a 1 to the denominator.

This has two main effects:
- No matter how small or even negative the $\beta_0+\beta_1X$ part is, the output will be strictly positive (the more negative the closer to $0$)
- As $\beta_0+\beta_1X$ gets very big, the $p(X)$ approaches one as we'd expect.

It is called logistic because if we take the $log$ of the [[Odds\|odds]] that is $\frac{p(x)}{1-p(x)}$ we are capable through that transformation to recover the linear model, this mean:
$$
ln(\frac{p(x)}{1-p(x)})=\beta_0+\beta_1X
$$

Before the application of the transformation analogous to the [[Activation Functions\|activation function]] in typical machine learning, the output of the linear model $\beta_0+\beta_1X$ is called a [[Logit\|logit]].

The logistic model is in the family of [[1. Cosmos/Linear Methods for Classification\|Linear Methods for Classification]] exactly because of the above, as we see the logit is linear in $X$.

Note that while we show that the logit of the logistic regression is a linear regression model you might mistakenly assume that the vector $\beta$ is estimated in the same way. Nothing could be further from the truth, while in [[1. Cosmos/Linear Regression\|Linear Regression]] we generally estimate the parameters directly though functions, for the logistic model we must use [[Maximum Likelihood Estimation\|Maximum Likelihood Estimation]] to find the answer.

This stems from the fact that while we recover the linear equation using


## What about if we have multiple features?
Well in such a case, you can easily extend the model to more features by analogy.
After all if we know that the logit for a single variable is simply $\beta_0+\beta_1X$, then it follows that for more variable, we'd just chuck em in the linear equation similarly to what we would do in [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]].

So
$$
ln(\frac{p(X)}{1-p(X)})=\beta_0+\beta_1X_1+\dots+\beta_nX_n$$

The rest is just a matter of solving for $p(X)$ which gives:
$$
p(X)=\frac{e^{\beta_0+\beta_1X_1+\dots+\beta_nX_n}}{1-e^{\beta_0+\beta_1X_1+\dots+\beta_nX_n}}
$$

Obviously throughout the way we assumed $n$ total predictors not counting the intercept.

Covered more in depth in [[1. Cosmos/Multinomial Logistic Regression\|Multinomial Logistic Regression]].

In the case of more classes while in theory we can still deal with it by adding more equations for everything tht we are tryign to compute (one probability for each class or $K-1$ depending of if we use the softmax or traditional approach), weird errors can ensue so as a result when we have more than two classes it is often a better idea to just another method like [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]] which better copes with those problems than [[1. Cosmos/Logistic Regression\|Logistic Regression]]—if we are adamant on using linear decision boundaries, or just any other method that better copes with more classes if not.


## References
  