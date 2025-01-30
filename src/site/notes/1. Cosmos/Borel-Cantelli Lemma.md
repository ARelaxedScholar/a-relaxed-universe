---
{"dg-publish":true,"permalink":"/1-cosmos/borel-cantelli-lemma/","created":"2025-01-22T11:17:13.948-05:00","updated":"2024-05-29T18:23:44.871-04:00"}
---

202405291748
Status: #idea
Tags: [[1. Cosmos/Probability Theory\|Probability Theory]]
State: #nascient
# Borel-Cantelli Lemma
The Borel-Cantelli Lemma is a lemma that you use when you want to find the probability of $\liminf A_n$ and $\limsup A_n$. In other words, it's a lemma you use when you want to find the probability of a sequence of events $A_n$ failing to occur only a finite number of times ($\liminf A_n$) or a sequence of events $A_n$ occurring infinitely many times ($\limsup A_n$)

>[!note]
>Remark that $\liminf A_n \subseteq \limsup A_n$, therefore if $\liminf A_n$ occurs, $\limsup A_n$ does as well

Intuitively, the probability of any of the above is always either $1$ or $0$. Either something will occurs infinitely many times, or it will not.

It makes the really dicey problem of proving the probability of infinite events almost trivial.

## The Lemma
Under a [[1. Cosmos/Probability Spaces\|probability space]] $(\varOmega, \mathscr F, P)$ and given a set of events $E_i \in \mathscr F$ ($E_i$ is always in $\mathscr F$ if $E_i$ is an event but wtv), then:
1. $$
\sum_{i=1}^\infty P(E_i)<\infty \implies P(\limsup E_n) = 0 \text{ or in other words, }E_n \text{ does NOT occur infinitely often}
$$
2. $$
\begin{align}
\text{Given a collection of independent events } E_i:\\
\sum_{i=1}^\infty E_i &< \infty \implies P(\limsup E_i) = 0 \text{, same as 1}\\
&= \infty \implies P(\limsup E_i) = 1, \text{ so } E_i \text{ does occur infinitely often}
\end{align}
$$
Recall as well that $\liminf A_n = \limsup A_n^c$ and realize that we can now do whatever we want.
Observe as well that if $\limsup A_n$ does not occur, it follows that $\liminf A_n$ does not as well.

Both proofs will use [[1. Cosmos/Fatou's Lemma\|Fatou's Lemma]] and the continuity of probability measure (the fact we can move $\lim$ in and out of parentheses to solve the problem).
### Part 1
Intuitively this makes sense, after all if I know that the sum of probability of my events is not infinite, that means that not infinitely many of them occur since whatever that sum was an infinite sum. If it does converge to some value let's say after n terms, then from the n +1  term and henceforth, the rest of the summation has to converge to $0$. 

Then using that and [[1. Cosmos/Fatou's Lemma\|Fatou's Lemma]] which tells us that probability measures are continuous and that we can move the $\lim$ operator in and out of the measure, we can bring the $\lim$ into the parentheses to obtain what we want.

What exactly I mean is left to the future me to remember when I go through the proof.


### Part 2
The first part of the second part is identical to [[1. Cosmos/Borel-Cantelli Lemma#Part 1\|#Part 1]] whether or not there is independence.
So part 2 consists in showing that if $P(\lim sup E_i)$ diverges (so is $\infty$) its probability is $1$.


## References
