---
{"dg-publish":true,"permalink":"/1-cosmos/cumulative-density-function/"}
---

202405301238
Status: #idea
Tags: [[1. Cosmos/Probability Theory\|Probability Theory]]
State: #nascient
# Cumulative Density Function
The definition of a cumulative density function often shortened cdf, is as follows:
$$
F(x) = P(X\in(-\infty,x])
$$
So we see the **cumulative nature**, what is the probability that $X$ is at value $x$ or anything below that. Therefore it is **non-decreasing**.
It is also sometimes represented as 
$$
P(X\leq x) \text{ or } P(\{w: X(w) \leq x\}) \text{ or } P(X^{-1}(-\infty, x])
$$
All of these notations are equivalent, but most of the time the first one is used.

It is strongly related to [[1. Cosmos/Probability Density Functions\|Probability Density Functions]] or [[1. Cosmos/Probability Mass Function\|Probability Mass Function]] and their associated [[1. Cosmos/Random Variable\|Random Variable]], but be careful rigorously a cumulative density function is not defined as the integral of a [[1. Cosmos/Probability Density Functions\|pdf]] or any such nonsense, in fact quite often we will have a cumulative density function without a pdf even existing. As long as you have a [[1. Cosmos/Probability Spaces\|probability space]], which we always do (lel). All you need to do to compute the cdf is to feed the set $(-\infty,x]\cap \varOmega$ to your [[1. Cosmos/Probability Measure (According to Kolmogorov)\|probability measure]] $P$)

## References
