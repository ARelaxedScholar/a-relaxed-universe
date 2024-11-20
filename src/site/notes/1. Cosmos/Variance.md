---
{"dg-publish":true,"permalink":"/1-cosmos/variance/","created":"2024-08-31T23:47:14.119-04:00","updated":"2024-05-30T13:31:15.241-04:00"}
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

## References
[[1. Cosmos/Expected Value\|Expected Value]]