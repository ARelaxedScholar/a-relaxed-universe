---
{"dg-publish":true,"permalink":"/1-cosmos/moment-generating-function/"}
---

202405232040
Status: #idea
Tags: [[Probability\|Probability]]
# Moment Generating Function
It is a function defined as:
$$
M_X(t)=E[e^{tx}] \text{, if } E(e^{tx}) < \infty \text{ for }t \in (-h,h)
$$
Which when we take the derivatives (and set $t$ to $0$), we obtain the [[Moments\|moments]] of a given random variable. It uses the fact that $e^{tX}$ can be written as the following series $1+tE[X]+\frac{t^2}{2!}E[X^2]+\dots$

This gives a compact and simple way to compute all the moments of a random variable from one equation instead of having to repeatedly compute them manually as follows for the $n_{th}$ moment. For some functions with complicated [[1. Cosmos/Probability Density Functions\|pdfs]] the moment generating functions give us a straightforward way to compute arbitrarily many moments.
$$
E[X^n]=\intop_{-\infty}^{\infty}x^np_X(x)dx
$$
Note that as long as we take enough derivatives both are equivalent.

## References
[A good video explaining it](https://www.youtube.com/watch?v=cbmfYoepHPk)