---
{"dg-publish":true,"permalink":"/1-cosmos/measure/"}
---

202405221247
Status: #idea
Tags: [[Measure Theory\|Measure Theory]]
# Measure
A measure typically denoted $\mu$ is a special type of function that maps subsets of a [[1. Cosmos/Sigma-Algebra\|Sigma-Algebra]] to the interval $[0,\infty]$ (this is a shorthand for $[0,\infty) \cup \infty$). The idea is that we want to be able to generalize the concept of [[Volume\|Volume]] (where here volume applies to the arbitrary-dimensional concept of "size" instead of specifically $3D$ volumes).

This special type of function must hold the two following properties:
- $\mu(\varnothing) = 0$, in other words the measure of the empty set is $0$.
- Given a countable number of **disjoint** sets $A_1, A_2, A_3, \dots$ then $\mu(\bigcup_{i=1}^{\infty} A_i) = \sum_{i=1}^\infty \mu(A_i)$. In other words, if I have arbitrarily many patches of lands around the Earth, it stands to reason that the amount of land I own should be the same whether I sum each individual patch, or those big patches all formed one big one.

For that reason, we will always have a positive "size", but could very well have an infinite size as well say the length of the entire real line $\mathbb R$.

Measures have a direct application in [[1. Cosmos/Probability Theory\|Probability Theory]], where we restrict their upper bound to be $1$ instead of $\infty$. Such measures are called [[1. Cosmos/Probability Measure (According to Kolmogorov)\|probability measures]].



## Cases
### Discrete Case
In the discrete case, where we have a [[Topological Space\|topological space]] (or just some space that accepts the concept of open sets), since the sample space is countable--finite or otherwise. We are able to assign a measure to each element by simply assigning a measure to each singleton element of the power set of that space. This is one of the rare cases where we will be able to use measures on the entire space.

### Continuous Case
In the continuous case, where we are dealing with a space that is uncountably infinite (ie: $\mathbb R^n$), the space becomes too big for us to assign a measure to each subset. Indeed it is provable by theorem that no measure can exist on such an expansive $\sigma-$algebra.

Therefore we are constrained to use what are called [[1. Cosmos/Borel-Sigma Algebras\|Borel-Sigma Algebras]] which are the smallest $\sigma-$algebra that contains all the open sets of a given space. This is cool because while they are massive as well (uncountably infinite), they are less uncountably infinite than the power set of our original space; enough so that we can define measures on them.

Those measures are referred to as [[1. Cosmos/Lebesgue Measures\|Lebesgue measures]]. This among other things is the key that unlocked the world of [[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]] and probability as we know it.

## Common Type of Measures
### Those that do not discriminate on any $X$
These measures are the first one we cover because of there polyvalency. While they do not represent "size" as precisely as we might want, they still have their use and have the advantage that they can be defined on any arbitrary topological space $X$.
#### Counting Measure
Simply count the number of elements in the subset. If its finite, assign it it's cardinality, if its infinite, then its size is $\infty$. You can easily convince yourself that it holds the first property.

For the second property, we say that $x + \infty=\infty$ no matter what $x$ is (including $\infty$), likewise $x\times\infty = \infty$ for all $x \in (0,\infty]$. For the case $0 \times \infty$, [[Measure Theory\|Measure Theory]] and other areas of math might disagree; while in many areas of math it is undefined, in measure theory we **typically** take it to be $0$ (as you would intuit).

So, the counting measure is this:
$$ 
\mu(A) = 
     \begin{cases}
       \text{|A|} &\quad\text{, if } |A| < \infty\\
       \infty &\quad\text{, else} \\
     \end{cases}
$$
with rules that:
$$
\begin{align}
x + \infty &= \infty \quad\text{for all }x \\
x \times \infty &= \infty \quad\text{for all } x \in (0,\infty]\\
0 \times \infty &= 0 \quad\text{most of the time}\\
\end{align}
$$
#### Dirac Measure for $p\in X$
It's a type of measure that assigns a measure to a positive value to a set only if it contains a given point based on which the measure is defined.

Think of a knight named Dirac who has to defend his queen, and there are two groups one with a hundred people--none of which the queen, and another with two individuals--and the queen is one of the two. Even if, the other group contained the entire world; even if the queen's group was composed of only herself, the queen's group would always have a measure of $1$ and the non-queen group of $0$.

A Dirac measure functions in a similar fashion, based on a fixed point we assign a measure to subsets based solely on whether they contain that point or not. That type of measure is generally denoted $\small\delta_p$ where $p$ is that fixed point:

$$ 
\small\delta(A) = 
     \begin{cases}
       \text{1} &\quad\text{, if } p \in A\\
       \infty &\quad\text{, else} \\
     \end{cases}
$$


### [[1. Cosmos/Lebesgue Measures\|Lebesgue Measures]]
We search for a measure that actually captures the usual idea of volume one would have, but that takes it to $n$-dimensional spaces. What exactly does that mean?:
1. $\mu([0,1]^n)=1$, in other words the volume of a $n-$dimensional unit cube will always yield $1$.
2. $\mu(x+A)=\mu(A)$, for all $x\in R^n$. This should be understood as the exact "coordinates" of the set $A$ are irrelevant. Two unit cubes one in Chicago, and the other in Tokyo are still unit cubes with the same volume. This property is called  [[Resistance to Translation\|Resistance to Translation]].

This is fundamentally what a [[1. Cosmos/Lebesgue Measures\|Lebesgue measure]] is. 
This is better treated in its own note.
## References
[Bright Side of Mathematics ~ Measure Theory](https://www.youtube.com/watch?v=7O7qPrNIt7w&list=PLBh2i93oe2qvMVqAzsX1Kuv6-4fjazZ8j&index=3)