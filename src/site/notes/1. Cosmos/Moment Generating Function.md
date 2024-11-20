---
{"dg-publish":true,"permalink":"/1-cosmos/moment-generating-function/","created":"2024-08-31T23:47:13.987-04:00","updated":"2024-06-17T17:23:53.986-04:00"}
---

202405232040
Status: #idea
Tags: [[Probability\|Probability]]
# Moment Generating Function
It is a special case of the [[Characteristic Function\|Characteristic Function]].
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

## Convenient Trick
No one has time to derivate the $k$ times to get the $k^{th}$ moment.
So when looking for the $k^{th}$ moment simply look for the coefficient of $t^k$ and multiply that by $k!$ factorial. (In the Taylor's Expansion)

If there is no $t^k$ in the Taylor's expansion, you know that the moment is $0$.

##
![Pasted image 20240531093334.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531093334.png)
## References
[A good video explaining it](https://www.youtube.com/watch?v=cbmfYoepHPk)