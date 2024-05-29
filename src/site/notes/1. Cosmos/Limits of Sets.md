---
{"dg-publish":true,"permalink":"/1-cosmos/limits-of-sets/"}
---

202405281741
Status: #idea
Tags: [[Calculus\|Calculus]]
State: #nascient
# Limits of Sets
The intuition is kind similar to the [[Limits of Sequences\|Limits of Sequences]], but since operation on sets are different than operations on regular numbers, we need to set the stage. Like for sequence of numbers, $\lim A_n$ exists precisely when $\liminf A_n=\limsup A_n$.

First, limits of sets will involve unions or intersections taken to some value, typically infinity.

The two most important to keep in mind is that for an arbitrary sequence $A_n$
$$
\limsup A_n = \bigcap_{n=1}^\infty\bigcup_{m=n}^{\infty} A_n
$$
$$
\liminf A_n = \bigcup_{n=1}^{\infty}\bigcap_{m=n}^\infty A_n
$$
A mnemonic trick to remember it is that the superior man gives what he has (hand pointing down), before asking for more.
While the inferior man asks before giving.

For sets, an **equivalent definition** is:
![Pasted image 20240528174719.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240528174719.png)

Which is read as $\limsup A_n$ occurs if $A_n$ occurs an infinite amount of times. On the other hand, $\liminf A_n$ occurs if $A_n$ fails to occur only a finite number of times.

Keep in mind that $\liminf A_n \subseteq \limsup A_n$, therefore if we know that $\limsup A_n$ occurred we do not necessarily know $\liminf A_n$ occurred. BUT if $\liminf A_n$ occurs, we know that $\limsup A_n$ definitely occurred.

## Result for Increasing and Decreasing Set Sequences
It is fairly straightforward and this left as an exercise to the reader to show that:
$\lim A_n$ is $A_n$ is an increasing sequence is equal to $\bigcup_{i=1}^\infty A_i$
and
$\lim A_n$ for a decreasing sequence is equal to $\bigcap_{i=1}^\infty A_i$

## References
