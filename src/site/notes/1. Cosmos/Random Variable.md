---
{"dg-publish":true,"permalink":"/1-cosmos/random-variable/","created":"2024-08-31T23:47:13.736-04:00","updated":"2024-05-30T13:43:47.626-04:00"}
---

202405171700
Status: #idea
Tags: [[Probability\|Probability]], [[Statistics\|Statistics]]
# Random Variable
In the formal mathematical language of [measure theory](https://en.wikipedia.org/wiki/Measure_theory "Measure theory"), a random variable is defined as a [measurable function](https://en.wikipedia.org/wiki/Measurable_function "Measurable function") from a [probability measure space](https://en.wikipedia.org/wiki/Probability_measure_space "Probability measure space") (called the _sample space_) to a [measurable space](https://en.wikipedia.org/wiki/Measurable_space "Measurable space").

Indeed a random variable is a [[1. Cosmos/Measurable Maps\|measure map]] of one dimension where the space being mapped to is the real line $\mathbb R$.

## Continuous Random Variables
$X$ is a continuous random variable if $F$ (the [[1. Cosmos/Cumulative Density Function\|Cumulative Density Function]] of $X$) is continuous.
Observe that $f(x)$ (if it exists) may not be continuous, this does **NOT** mean that the random variable is also not continuous. 

Note that if $f(x)$ **is** continuous, then it's cumulative density function (and therefore the associated random variable) will be continuous.

In general to check if a [[1. Cosmos/Cumulative Density Function\|Cumulative Density Function]] is continuous from the [[1. Cosmos/Probability Density Functions\|probability density function]], you integrate the function and then check if there's any discontinuity (weird jumps) in the functions' path (just graph it).
## References
