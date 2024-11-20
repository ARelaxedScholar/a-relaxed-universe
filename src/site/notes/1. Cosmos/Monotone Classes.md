---
{"dg-publish":true,"permalink":"/1-cosmos/monotone-classes/","created":"2024-08-31T23:47:13.713-04:00","updated":"2024-05-24T17:03:52.672-04:00"}
---

202405241514
Status: #idea
Tags: [[Measure Theory\|Measure Theory]]
State: #nascient
# Monotone Classes
They are a concept strongly connected to [[Sigma Algebra\|$\sigma$-algebras]]. In fact, a field (algebra  ) $\mathscr B$ is a $\sigma-algebra$ if and only if it is also a monotone class. A class is another word for [[1. Cosmos/Algebra\|algebras]].

SO what the heck is a monotone class? A monotone class is a set that is closed under monotone limits of increasing and decreasing sets.

We must note that for increasing sets their limit is given by:
$$
\bigcup_n A_n
$$
while for increasing their limit is given by:
$$
\bigcap_n A_n
$$

In other words, a class is a monotone class if the union of a sequence of increasing sets (sets such that $A_i \subseteq A_j$ for all $i<=j$) is in the class AND if the intersection of a sequence of decreasing sets (sets such that $A_i \supseteq A_j$ for all $i <= j$) are in the class.
## References
