---
{"dg-publish":true,"permalink":"/1-cosmos/probability-measure-based-on-expected-value/","created":"2025-01-22T11:17:14.154-05:00","updated":"2024-05-29T13:50:04.887-04:00"}
---

202405291209
Status: #idea
Tags: [[1. Cosmos/Probability Theory\|Probability Theory]]
State: #nascient
# Probability Measure (Based on Expected Value)
## Why?
It is a competitor to the trusted definition of [[1. Cosmos/Probability Measure (According to Kolmogorov)\|Probability Measure (According to Kolmogorov)]] that is purported to make more sense, because it is founded on a concept that even non mathematicians are familiar with: [[Arithmetic Mean\|Arithmetic Mean]].

Fundamentally, an expected value is an average and in the context of probability represents the value that we expect some [[1. Cosmos/Random Variable\|Random Variable]] to take after $n$ samples (potentially infinite.) And it is computed by basically taking a weighted average. This allows us to skip [[Measure Theory\|measure theoretic nonsense]] (jk, I like measure theory) and directly start talking of [[1. Cosmos/Probability Theory\|Probability Theory]]. Which is definitely a huge advantage if you're a starry eyed learner who decided to learn probability for whatever reason and that get hit with a wall of convergence theorems, limits, and just [[Measure Theory\|Measure Theory]] concepts that must be front-loaded before you get to even see what probability even means.

## Definition of Expected Value
First what is an [[1. Cosmos/Expected Value\|Expected Value]]? 
For some [[1. Cosmos/Random Variable\|random variable]] $X$, the expected value is an operator such that:
1. If $X \geq 0 \implies E(X) \geq 0$
2. If $c \in \mathbb R \implies E(cX) = cE(X)$ 
3. $E(X_1+X_2)=E(X_1)+E(X_2)$
4. For some constant $c$, $E(c)=c$
5. If $0\leq X_n(\omega)\uparrow \text{in } n \text{ such that } X_{n+1}(\omega) \geq X_n(\omega) \text{ for all } n \implies E(X_n)\uparrow E(X)$ [[Monotone Convergence Theorem\|Monotone Convergence Theorem]]

Most of these properties are intuitive except $5$. The last property essentially states that if $X_n$ is an increasing sequence with respect to $n$, the expected value of $E(X_n)$ will grow towards $E(X)$ (or approach from the left) as $n$ approaches infinity. And $X$ here that seems to come out of nowhere is understood to be the pointwise limit of the sequence $X_n$,  in other words what happens when $n$ gets really big, so $X=\lim_{n \rightarrow \infty} X_n$.

The idea is that $X$ encapsulates the entire sequence $X_n$ and for that reason we drop the index.

With this in mind you can see that an equivalent statement to $5$ is :
If $X_n(\omega)\uparrow \text{in } n \text{ such that } X_{n+1}(\omega) \geq X_n(\omega) \text{ for all } n \implies \lim_{n \to \infty} E(X_n)=E(\lim_{n \to \infty} X_n)$ [[Monotone Convergence Theorem\|Monotone Convergence Theorem]]

>[!intuition]- My Current Intuition of the Statement
 > I currently understand it as $X$ is the pointwise limit of the sequence $X_n$ which is increasing. It is so labelled, because it encapsulates the behaviour of the entire sequence $X$. For that reason its definition is $\lim X_n$ as $n$ approaches infinity. Now this $X$ could exist (if $X_n$ converges) or not. But since we always assume that $X_n$ is non-negative (no variables cancelling each other possible) and non-decreasing (no oscillations possible), it follows that $X$ always exist in $\mathbb R \cup \infty$ (in probability, since we operate in the extended real number system, a limit that is $\infty$ or $-\infty$ is said to exist). if its finite then it is effectively an upper bound of the expected value of our sequence $X_n$ since $X_n$ is increasing, and considering some parts when taking our expected value can never be bigger than taking the whole by extension of axiom 1 (and the fact it is increasing). If its not finite, then it's also an upper bound but we will require more analysis to see if such a result is expected or if its indicative of a wrong model. Whichever it is will be meaningful for us.
 > 
 > After all, now that we have found our maximum, it follows that under the aforementioned conditions, as we add more and more random variables, we can only increase (or fill) towards that upper bound.


Fundamentally, these are axioms so you can just take them as fact and go on your merry way, but if you need intuition (and a rigorous proof), especially for the [[Monotone Convergence Theorem\|Monotone Convergence Theorem]], it is a theorem from [[Measure Theory\|Measure Theory]] and it is explained in its own note.

### So?
With the above established, we can say that as long as $E$ is defined in such a way that all these properties is maintained, it is an [[1. Cosmos/Expected Value\|Expected Value]]. Obviously if whatever definition of "expected value" we have fails with one of those properties it is NOT an expected value.

From there you see that the standard definition of expected values as:
**Discrete case**
$$
\sum_{i=1}^nxp_x
$$
**Continuous case**
$$
\intop_{-\infty}^\infty xf_x~dx
$$
Will hold all the above properties, and since $p_x$ and $f_x$ are probability measures (not yet defined here, don't worry) that will range between $0$ and $1$, we are effectively taking a weighted average.

## Probability using Expected Value
Well we recall [[1. Cosmos/Indicator Functions\|Indicator Functions]], which are defined in their own notes.

For some event $A$ and indicator function $I_A$, we say the following:
$$
P(A)=E(I_A(\omega))=E(I_A)
$$
As simple as that!
All the properties we've proved for [[1. Cosmos/Probability Measure (According to Kolmogorov)\|Probability Measure (According to Kolmogorov)]] apply here.


## References
