---
{"dg-publish":true,"permalink":"/1-cosmos/chebyshev-s-inequality/","created":"2024-08-31T23:47:13.497-04:00","updated":"2024-05-30T21:24:07.469-04:00"}
---

202405302108
Status: #idea
Tags: 
State: #nascient
# Chebyshev's Inequality
![Pasted image 20240530212406.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240530212406.png)

Chebyshev's Inequality really is just a special case of [[1. Cosmos/Markov's Inequality\|Markov's Inequality]] where we replace $X$ with $X-b$:
$$
P(|X-b|\geq a) \le \frac{E(|X-b|)}{a}
$$
Equivalently we can do the following:
$$
P[(X-b)^2 \ge a^2] \le \frac{E[(X-b)^2]}{a^2}
$$

Observe that $(X-b)^2 \ge a^2$ exactly when $|X-b|\ge a$, so they are really equivalent statements!

Now how do we put that in the format we're familiar with?
Simply pick $b=\mu$ and $a=k\sigma$ such that:
$$
\begin{align}
P(|X-\mu| &\ge k\sigma) \le \frac{E[(X-\mu)^2]}{k^2\sigma^2} \text{, we write the LHS and RHS in different but equivalent manners}\\
&\le \frac{\sigma^2}{k^2\sigma^2} \text{, we can replace numerator by Var(X)}\\
&\le \frac{1}{k^2}
\end{align}
$$
## References
