---
{"dg-publish":true,"permalink":"/1-cosmos/variance/","created":"2024-08-31T23:47:14.119-04:00","updated":"2024-12-13T08:35:57.349-05:00"}
---

202405301306
Status: #idea
Tags: [[1. Cosmos/Probability Theory\|Probability Theory]]
State: #nascient
# Variance

## Elementary Probability
This $E[(X-E(X))^2]$ or equivalently $E[(X-\mu)^2]$
It represents the variation around a mean squared.

## In MAT3172
The meaning is the same, but we have a parti pris for the definition and we do not use [[1. Cosmos/Probability Density Functions\|Probability Density Functions]] since we acknowledge they might not exist; plus we do more rigorous math so we work on [[1. Cosmos/Probability Spaces\|Probability Spaces]] instead.

Therefore we need to change the way we compute our variance and the formula is impacted by the similar change in [[1. Cosmos/Expected Value#In MAT3172\|Expected Value#In MAT3172]]:
$$
\begin{align}
Var(X)&=\intop^\infty_{-\infty}(x-\mu)^2 dF(x)\\
&= E(X^2)-\mu^2
\end{align}
$$

Observe that if $E(X_\mu)^2 = 0$, then by how this result is derived and by the fact $F(x)$ is non-negative and non-decreasing, we have to conclude that:
$$
P(X=\mu)=1
$$
This is often said, $X$ equals $\mu$ almost surely.

## In Machine Learning
In this context there are two important and non-overlapping type of variance that is $Var(f(x))$ iften understood as the irreducible error $\epsilon$. This represents the part of the variance around the mean that cannot be accounted due to intrinsic variability in the response itself.

On the other hand there is the $Var(\hat f(x))$ which is the variance of the predictor model itself which might sound weird as predictors being functions will always output the same value given the same $x$ and should be $0$, no? Yes, but not quite. In this context, this variance represents how much the fitof the model would have changed given a **DIFFERENT TRAINING SET** and is a direct counterpart to the [[Bias\|Bias]], as a a general rule, models that are more complex/flexible have a lower [[Bias\|Bias]] as they basically make no errors due to the rigidity of the model and the assumptions they make, but they have high variance since they capture the data so well that logically given new data they will have to adapt. 

This is the opposite for high bias methods which are highly rigid, they make and project their assumptions unto the data whether it fits the dataset or not. Which means that assuming that all the datasets are sampled from the same population, the fit of the model would be roughly the same leading to a lower variance.
## References
[[1. Cosmos/Expected Value\|Expected Value]]