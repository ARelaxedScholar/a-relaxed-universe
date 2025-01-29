---
{"dg-publish":true,"permalink":"/1-cosmos/naive-bayes/","created":"2025-01-22T11:17:14.314-05:00","updated":"2024-12-13T09:25:34.157-05:00"}
---

202412111029
Status: #idea
Tags: [[Generative Models\|Generative Models]]
State: #nascient
# Naive Bayes

It is a cousin of the [[1. Cosmos/Discriminant Analysis\|Discriminant Analysis]] models such as [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]] and [[1. Cosmos/Quadratic Discriminant Analysis (QDA)\|Quadratic Discriminant Analysis (QDA)]].

While they attempt to solve the same problem, that is generating the posterior probability through estimation of the prior and likelihood of the classes, the Naive Bayes makes an assumption that is arguably stronger than even its cousins.

While [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]] makes the assumptions of normality of $X$ within the classes and of equal covariance across classes leading us to having to estimate only the means within the respective classes with one pooled covariance matrix, and the [[1. Cosmos/Quadratic Discriminant Analysis (QDA)\|Quadratic Discriminant Analysis (QDA)]] keeps the normality assumption while dropping the often untenable assumption of equal covariance, Naive Bayes flips the bird and just says: "You know what, all the predictors are conditionally independent."

By that we mean that while we would expect that $k$ will have higher readings of a given class and lower readings of another class on average as compared to some other class $k'$, when fixing our attention to a single class $k$, the covariance between predictors is $0$.

In other words, $P(x|Y=C_k)=P(x_1|Y=C_k)\times P(x_2|Y=C_k) \times \dots \times P(x_p|Y=C_k)$.

Plugging it into Bayes theorem as for the other models we get:
$$
P(Y=C_k|X=x)=\frac{P(C_k)\textcolor{yellow}{P(x_1|Y=C_k)\times P(x_2|Y=C_k) \times \dots \times P(x_p|Y=C_k)}}{\sum_{i=1}^KP(C_i)\times P(x|Y=C_k)\times P(x_1|Y=C_k)\times P(x_2|Y=C_k) \times \dots \times P(x_p|Y=C_k)}
$$


Though it's simplifying assumption, Naive Bayes increases the bias as we essentially don't have to fit covariance matrices, but decreases the variance. This means that we would expect it to come into its own in cases where $p$ is big or when $n$ is smaller, that is in contexts where the bias is important to prevent overfitting.

Naive Bayes success can be puzzling as after all, in most contexts, we'd expect the assumption to be entirely false.

Still it can be explained through the lens of the [[Bias-Variance Tradeoff\|Bias-Variance Tradeoff]], thanks to the assumptions it makes we require less parameters to fit at the cost of bias, but considering the fact that for a rigorous estimation of the likelihoods would require ungodly amounts of data which in most cases are not even available, this bias ends up smaller than the great variance that would arise if other methods were used simply because generally the lack of data prevents us from actually estimating the parameters.

As a result, even though the assumptions are really strong, it often gives pretty good results.



## References
olio