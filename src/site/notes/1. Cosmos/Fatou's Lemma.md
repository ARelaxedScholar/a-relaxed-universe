---
{"dg-publish":true,"permalink":"/1-cosmos/fatou-s-lemma/","created":"2025-01-22T11:17:14.258-05:00","updated":"2024-05-29T17:35:36.502-04:00"}
---

202405291517
Status: #idea
Tags: [[1. Cosmos/Probability Theory\|Probability Theory]], [[Measure Theory\|Measure Theory]]
State: #nascient
# Fatou's Lemma
Let $A_n$ be a family of [[1. Cosmos/Event\|events]].
1. $P(\liminf A_n) \leq \liminf P(A_n) \leq \limsup P(A_n) \leq P(\limsup A_n)$
2. If $\lim A_n$ exists then $\lim P(A_n) = P(A)$. In other words, if $A_n \to A \implies P(A_n) \to P(A)$. In other words, P is continuous.

### Preliminary Lemma: 
$P(\lim A_n) = \lim  P(A_n)$ if $A_n$ is decreasing, or $A_n$ is increasing.
I leave this as a proof to future me.

## Part 1
If you can prove the Lemma, then Fatou's Lemma first part follows after simple manipulation of the terms inside the parentheses. Hint (in what other ways can you write $\lim inf A_n$ and $\lim sup A_n$)

## Part 2
It follows pretty nicely from part $1$.
We start by noticing that $\lim A_n = A$ exists exactly when $\liminf A_n = \limsup A_n$.

So we obtain:
$$
A = \lim A_n = \liminf A_n = \limsup A_n
$$
Plugging that into part $1$ we get:
$$
P(A) = P(\liminf A_n) \leq \liminf P(A_n) \leq \limsup P(A_n) \leq P(\limsup A_n) = P(A)
$$
Since we squeezed the top and the bottom between $P(A)$ the chain of inequalities has to go to $P(A)$.

And so it follows that as $A_n \to A$, $P(A_n) \to P(A)$.
## References
