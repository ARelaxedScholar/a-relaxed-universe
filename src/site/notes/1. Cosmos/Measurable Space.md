---
{"dg-publish":true,"permalink":"/1-cosmos/measurable-space/"}
---

202405240848
Status: #idea
Tags: [[Measure Theory\|Measure Theory]]
State: #nascient
# Measurable Space
A sample space equipped some $\sigma-$algebra $\varXi$  is called a [[1. Cosmos/Measurable Space\|measurable space]].
It is denoted as follows:
$$
(\varOmega, \varXi)
$$

Probability is really just a special kind of [[Measure Theory\|Measure Theory]].

One must understand what is a [[1. Cosmos/Measure\|measure]].
A measure is a **function** say $\psi$ from the $\sigma-$algebra that we elected to the interval $[0, \infty]$ (this is not a typo, we can actually send values to infinity) such that:
1. $\psi(\varnothing) = 0$
2.  If $A_1, A_2, \dots$ is a countable collection of **disjoint** $\varXi-$measurable sets, then:
   $$
   \psi(\bigcup_{i=1}^\infty) = \sum_{i=1}^{\infty}\psi(A_i)
   $$

All we are saying is that some empty set should be measured as $0$, and that if I have some countable number of disjoint sets, I should be able to get the measure of the **whole** (union) by summing the **individual** measures.

This is eerily similar to how we define the probability of disjoint events.

## The $\sigma-$algebra of Events
A [[Measure Space\|Measure Space]] is the combination of a measurable space denoted in these notes $\varXi$ and some [[1. Cosmos/Measure\|measure]] denoted $\psi$. It is written as:
$$
(\varOmega, \varXi, \psi)
$$
We require that $\psi(\varOmega)$ is well defined:
- if $\psi(\varOmega) < \infty$ then $\psi$ is a finite measure.
- if $\psi(\varOmega) = \infty$, then $\psi$ is an infinite measure
- if $\psi(\varOmega) = 1$, then $\psi$ is a **[[1. Cosmos/Probability Measure\|Probability Measure]]** (yessir!)

In the last case, we denote $\psi$ with a capital $\mathbb P$. 

So we can denote it ($\varOmega, \varXi, \mathbb P$) or say that $\mathbb P$ is a probability measure on the [[1. Cosmos/Measurable Space\|measurable space]] ($\varOmega, \varXi$)!
### So the measure axioms applied to Probabilities
1. $\mathbb P(\varnothing) = 0$
2. $\mathbb P(\varOmega) = 1$
3. If $A_1, A_2, \dots$ are disjoint $\varXi-$measurable sets, then
   $\mathbb P(\bigcup_{i=1}^{\infty} A_i) = \sum_{i=1}^{\infty} \mathbb P(A_i) \le 1$

So as we see we can define a probability space which is nothing more than a measurable space where the measure is a probability measure space is $(\varOmega, \varXi, \mathbb P)$.

From now on, I'll denote the probability measure as $P$. From this, we can now define [[1. Cosmos/Event\|events]] rigorously. They are nothing more than the $\varXi-$measurable sets of our probability measure space. 

This now answers why we specified "subsets under consideration" if a subset is not in our $\varXi-$algebra, then the measure defined on our [[1. Cosmos/Measurable Space\|measurable space]] does not consider it. Therefore it does not have a probability.
### The Magic
There is absolutely no prescriptions (or right way) as to how to define a [[1. Cosmos/Probability Measure\|Probability Measure]] or the $\sigma-$algebra for that matter.

Any arbitrary such space you can cook up, as long as you ensure it has the aforementioned properties is a totally valid probability measure. This give us a really expansible and rich soil to construct our [[1. Cosmos/Probability Theory\|Probability Theory]].



## References

