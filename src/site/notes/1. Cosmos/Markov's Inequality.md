---
{"dg-publish":true,"permalink":"/1-cosmos/markov-s-inequality/","created":"2024-08-31T23:47:13.472-04:00","updated":"2024-05-30T21:08:30.826-04:00"}
---

202405301409
Status: #idea
Tags: [[1. Cosmos/Probability Theory\|Probability Theory]], [[Important Inequalities\|Important Inequalities]]
State: #nascient
# Markov's Inequality
![Pasted image 20240530210558.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240530210558.png)
Markov's Inequality states that given an $a$ that is positive, and an $X$ that is non-negative, the following holds:
$$
P(X \geq a) \leq \frac{E(X)}{a}
$$
It is possible to deal with random variables that are negative by taking the absolute value so that:
$$
P(|X| \geq a) \leq \frac{E(|X|)}{a}
$$

It can be derived fairly simply by taking the expected value of the two functions shown above.
It is a general case of [[1. Cosmos/Chebyshev's Inequality\|Chebyshev's Inequality]].
## References
