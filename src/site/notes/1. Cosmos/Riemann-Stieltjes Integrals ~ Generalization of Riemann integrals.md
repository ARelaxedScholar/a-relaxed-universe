---
{"dg-publish":true,"permalink":"/1-cosmos/riemann-stieltjes-integrals-generalization-of-riemann-integrals/"}
---

202405301320
Status: #idea
Tags: [[Calculus\|Calculus]], [[Integrals\|Integrals]]
State: #nascient
# Riemann-Stieltjes Integrals ~ Generalization of Riemann integrals

We can generalize [[1. Cosmos/Riemann Integrals\|Riemann Integrals]] to arbitrary functions instead of always using $x$ (which we remark is a non-decreasing function) as follows:

$$
\intop_{a}^{b}f(x) ~d\alpha(x) = \lim_{n\to \infty} \sum f(x_i)(\alpha(x_i)-\alpha(x_{i-1}))
$$
For $\alpha$ which is non-decreasing. This can be used if $\alpha$ has finite variation, but as I am typing this I am not too sure what that means.

Observe that by our trusty chain rule, the *LHS* of the above can be written as:
$$
\intop_{a}^{b}f(x) ~d\alpha(x) = \intop_{a}^{b}f(x) ~\alpha'(x)dx \text{, assuming that } \alpha(x) \text{ is differentiable}
$$
Now note that if $\alpha(x)=x$ then this becomes a [[1. Cosmos/Riemann Integrals\|Riemann integral]]. There are cases where $\alpha$ is not differentiable though.

Based on this definition we can define many things such as:
- [[1. Cosmos/Cumulative Density Function\|cumulative density functions]]
- [[1. Cosmos/Expected Value#In MAT3172\|expected values]]
- [[1. Cosmos/Variance#In MAT3172\|variances]]
## References
