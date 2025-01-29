---
{"dg-publish":true,"permalink":"/1-cosmos/cumulative-density-function/","created":"2025-01-22T11:17:13.961-05:00","updated":"2024-06-03T16:31:25.510-04:00"}
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

Because of how they function, if you want to compute $P(X \le x)$, you can simply plug $x$ in your $F$.

But you're given a cdf, and you want to compute $P(a \le X \le b)$, you're going to need to remove the cumulative probability up to $a$ from the cumulative up to $b$. In this case we'd want to keep $a$ so we'd actually go $a^-$, in a continuous context this makes no difference, but in a discrete context this means decreasing by one.

## Continuous Cumulative CDF
The CDF is continuous

## Discrete Cumulative CDF
The CDF is a step-function, in other words $F'(x)=0$ except at jump points where $F'(x)$ does not exist.

## The Rest CDF
The CDF is not continuous, but is not a step function either.
## References
