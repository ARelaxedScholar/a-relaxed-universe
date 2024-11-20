---
{"dg-publish":true,"permalink":"/1-cosmos/sigma-algebra/","created":"2024-08-31T23:47:14.026-04:00","updated":"2024-05-24T08:58:29.287-04:00"}
---

202405240847
Status: #idea
Tags: [[1. Cosmos/Probability Theory\|Probability Theory]], [[Measure Theory\|Measure Theory]]
State: #nascient
# The Saviour of Algebra : The $\sigma-$Algebra
Well, all a $\sigma-$algebra is, is some [[1. Cosmos/Probability Spaces#What is an Algebra?\|algebra]] which is closed under **countably** infinite unions. In other words, the following is true:
$$
\begin{align}
\text{If }A_1, A_2, \dots &\text{ are all in the algebra } \varXi \text{ under consideration, then:}\\
&\bigcup_{i=1}^\infty A_i = \bigcup_{i \in \mathbb N} A_i \in \varXi
\end{align}
$$
This addition is all we lacked to start developing [[1. Cosmos/Probability Theory\|Probability Theory]].
*Is this true for the intersections as well?*

Please be aware that the $\sigma-$algebra can contain a finite number of elements, or an uncountable infinite number of elements, as long as it's close under infinite unions we are gucci.

Also $\sigma-$algebra **IS** an algebra, after all the condition is stronger. You can convince yourself that the converse is not true.

Subsets which belong to a $\sigma-$algebra, here denoted $\varXi$ are called $\varXi-$measurable sets.  

### Countable vs Uncountable
#### Countable Sample Space
If our sample space $\varOmega$ is countable (finite or infinite), it is possible to define a $\sigma-$algebra which simply consists of **ALL** possible subsets of $\varOmega$ (denoted $2^\varOmega$), and therefore we can assign a probability to each outcome in the sample space. In such cases we are operating in what's called a [[1. Cosmos/Discrete Probability Spaces\|discrete probability space]].

This is important, because in such spaces even though the $\sigma-$algebra might be uncountably infinite (see [[Diagonalization Argument\|Diagonalization Argument]]), it is straightforward to define a probability function such that $\sum_{x\in\varOmega} p_x = 1$ and then assign to each event the probability of the sum of its elements. This is what we call a [[Discrete Probability Measure\|Discrete Probability Measure]]

### Uncountable Sample Space
If the sample space is uncountably infinite, no such trick exist. That's when $\sigma-$algebras really come into their own and [[1. Cosmos/Borel Sets\|Borel Sets]] really come into their own.


## References
