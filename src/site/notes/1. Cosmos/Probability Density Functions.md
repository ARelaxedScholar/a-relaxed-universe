---
{"dg-publish":true,"permalink":"/1-cosmos/probability-density-functions/"}
---

202405301312
Status: #idea
Tags: [[1. Cosmos/Probability Theory\|Probability Theory]]
State: #nascient
# Probability Density Functions
We say $f$ is the p.d.f for a [[1. Cosmos/Random Variable\|random variable]] $X$ if it is possible to write it as:
$$
0 \leq P(-\infty,x]=\intop^x_{-\infty}f(x)du
$$
Observe this forces:
1. $f \geq 0$
2. $\intop_{-\infty}^{\infty} f(x)~dx =1$, since $P(-\infty, \infty)=1$

While we are used to that being always the case in elementary probability it is not always possible.
## References
