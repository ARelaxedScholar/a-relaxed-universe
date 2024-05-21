---
{"dg-publish":true,"permalink":"/1-cosmos/probability-spaces/"}
---

202405201152
Status: #idea
Tags: [[Probability\|Probability]]
# Probability Spaces

## Before we Start (Our Lego Pieces)
These two things are the most fundamental building blocks of [[Probability\|Probability]] and are objects that we take as axiomatic. They are what define other elements and they are exactly what they sound like.

[[Random Experiment\|Random Experiment]]: It is an experiment (defined by the problem at hand) that can terminate in one of many outcomes, where the exact outcome is uncertain (hence random.) It is an idiomatic term that represents basically all problems in probability.

[[Outcome\|Outcome]]: It is typically denoted $\omega$ and it is an element of the [[Sample Space\|Sample Space]]  of a given [[Random Experiment\|Random Experiment]] ($\omega \in \varOmega$.) It is one of the possible ways in which the random experiment can conclude.

## What is the Sample Space
[[Sample Space\|A sample space]], typically denoted $\varOmega$, represents the set of all possible outcomes of a random experiment. 

For example, if I toss a coin once, **a possible and natural sample space** would be $\varOmega = \{H, T\}$, but observe that the experiment does not **force** the sample space. As in multiple totally valid sample spaces exist for a given random experiment, and me the--data scientist--is the one that chooses what my sample space is.

If instead, I am interested in how many times the coin tumbles in the air, even though the random experiment is the same (tossing a coin once), the sample space would now be $\varOmega = \{1,2,3,\dots\} = \mathbb N$.

Therefore, the sample space is defined both by the [[Random Experiment\|random experiment]] and the thing of interest.

The random of *random experiment* comes from the fact that the outcomes have an associated [[Probability\|probability]] and that we cannot control which $\omega-$labelled marble we draw from our big bag called $\varOmega$.

[[Finite Sample Spaces\|Finite Sample Spaces]]
[[Infinite Sample Spaces\|Infinite Sample Spaces]]
[[Countable Sample Spaces\|Countable Sample Spaces]]
[[Uncountable Sample Spaces\|Uncountable Sample Spaces]]

## What is an Event?
Informally, an [[Event\|event]] is any subset of of the sample space $\varOmega$ which is of interest to the experimenter. If we take a coin toss, technically it is possible for the coin to fall on its side and that neither tail nor head show up. This would be a possible outcome (that we might, or not account for) but not an event since we don't care about it.

An event will often be worded similarly to a filter in programming languages. Like we are trying to capture a subset of the data and think about its specific properties
```python
event_even = df.loc[df['count_of_heads'] % 2 == 0] # checking for even
```
### Consequences of this definition
- If something occurring is of interest, then it **not** occurring is also of interest (it's the dual of it in a sense)
```python
# if we try to create a event_even, then
even_even_prime = df.drop(event_even.index) # the odd subset is created at the same time
```
- If two events are occurring? Then their interaction with each other will be of interest as well. What is their union? their intersection?
- The sample space is always an [[Event\|event]] by definition, it is literally the thing we are working on. Our workbench so to speak.

These altogether give us what's referred to as an [[Algebra\|Algebra]].

## What is an Algebra?
A collection of subsets $\varUpsilon$ of a sample space $\varOmega$ such that:
- $\varnothing$ is in the set (since it's the complement of $\varOmega$)
- If $A$ is in the set $\varUpsilon$, then $\omega^c$ is in the set as well
- If $A$ and $B$ are in the set $\varUpsilon$, so is $A \cup B$.

If all three of these conditions holds, we have an [[Algebra\|algebra]].
Note that here the elements are sets themselves.
### Consequences of this definition
If $A_1, A_2, A_3, \dots, A_n$ are in $\varUpsilon$ then the following is true:
$$
\bigcup_{i=1}^n A_i  \text{ and } \bigcap_{i=1}^n A_i \in \varUpsilon
$$
Therefore under **finite** unions and intersections, the above is true.
We cannot make such guarantees at infinity, because infinity is weird.

*Try to prove it! hint: prove the first one, and then use a well known theorem to derive the second. (You'll need induction)*
#### Problems in Paradise
An algebra is not quite enough structure for us to study probability, more specifically the limitation of being closed under **finite** unions is just a little short of what we need.

Why? Because under those conditions there is no way to define events that are the union (or intersection) of infinitely many elements in our sample space!

Consider the following problem:
**Random Experiment**: I am in an infinite tower ascension novel where each floor constitutes a challenge either puzzle-strategy or battle. I happen to be great at battling, but not so great at puzzle-strategy games. The levels are generated randomly and I am fairly confident that if I encounter a puzzle-strategy games it is very likely that I fail.

Therefore, we are interested in the sequence of possible levels until we meet the first puzzle-strategy level (denoted $P$) as opposed to battle levels say $B$.

$\varOmega$ is therefore $\{P, BP, BBP, BBBP, \dots\}$.

Now let's say I am interested in the event that I encounter the first $P$ on a *odd floor*.
Then this subset of $\varOmega$ would be $\{P, BBP, BBBBP, \dots\}$.

Now observe that under the kind of algebra we have now, there is no construction that will yield for us this subset since if we partition the sample space so that each outcome is its own event, the subset of interested would  be represented by:
$$
\bigcap_{i=1,3,...}^\infty A_i
$$
The issue is that this is an infinite intersection. Which under our current rules no matter the algebra we make, no algebra can guarantee that this event will be in it (even if all the individual events are.) This is a huge problem since everything else, be it [[1. Cosmos/Probability Measure\|probability measure]], the definition of [[Probability\|probability]] itself and whatnot will be based on the assumption that our workbench contains all there is to consider.

In fact any event that would be represented as some elementary operation on an infinite number of sets would have the same problem. Since we have no guarantee it would be in any algebra, it could happen to be (after all $\varOmega$ is) but we cannot be certain ever.

## The Saviour of Algebra : The $\sigma-$Algebra
Well, all a $\sigma-$algebra is, is some [[1. Cosmos/Probability Spaces#What is an Algebra?\|algebra]] which is closed under **countably** infinite unions. In other words, the following is true:
$$
\begin{align}
\text{If }A_1, A_2, \dots &\text{ are all in the algebra } \varXi \text{ under consideration, then:}\\
&\bigcup_{i=1}^\infty A_i = \bigcup_{i \in \mathbb N} A_i \in \varXi
\end{align}
$$
This addition is all we lacked to start developing [[Probability Theory\|Probability Theory]].
*Is this true for the intersections as well?*

Please be aware that the $\sigma-$algebra can contain a finite number of elements, or an uncountable infinite number of elements, as long as it's close under infinite unions we are gucci.

Also $\sigma-$algebra **IS** an algebra, after all the condition is stronger. You can convince yourself that the converse is not true.

Subsets which belong to a $\sigma-$algebra, here denoted $\varXi$ are called $\varXi-$measurable sets.  

### Countable vs Uncountable
#### Countable Sample Space
If our sample space $\varOmega$ is countable (finite or infinite), it is possible to define a $\sigma-$algebra which simply consists of **ALL** possible subsets of $\varOmega$ (denoted $2^\varOmega$), and therefore we can assign a probability to each outcome in the sample space. In such cases we are operating in what's called a [[1. Cosmos/Discrete Probability Spaces\|discrete probability space]].

This is important, because in such spaces even though the $\sigma-$algebra might be uncountably infinite (see [[Diagonalization Argument\|Diagonalization Argument]]), it is straightforward to define a probability function such that $\sum_{x\in\varOmega} p_x = 1$ and then assign to each event the probability of the sum of its elements. This is what we call a [[Discrete Probability Measure\|Discrete Probability Measure]]

### Uncountable Sample Space
If the sample space is uncountably infinite, no such trick exist. That's when $\sigma-$algebras really come into their own and [[Borel Sets\|Borel Sets]] really come into their own.

## What is A Measurable Space?
A sample space equipped some $\sigma-$algebra $\varXi$  is called a [[Measurable Space\|measurable space]].
It is denoted as follows:
$$
(\varOmega, \varXi)
$$

Probability is really just a special kind of [[Measure Theory\|Measure Theory]].

One must understand what is a [[Measure\|measure]].
A measure is a **function** say $\psi$ from the $\sigma-$algebra that we elected to the interval $[0, \infty]$ (this is not a typo, we can actually send values to infinity) such that:
1. $\psi(\varnothing) = 0$
2.  If $A_1, A_2, \dots$ is a countable collection of **disjoint** $\varXi-$measurable sets, then:
   $$
   \psi(\bigcup_{i=1}^\infty) = \sum_{i=1}^{\infty}\psi(A_i)
   $$

All we are saying is that some empty set should be measured as $0$, and that if I have some countable number of disjoint sets, I should be able to get the measure of the **whole** (union) by summing the **individual** measures.

This is eerily similar to how we define the probability of disjoint events.

## The $\sigma-$algebra of Events
A [[Measure Space\|Measure Space]] is the combination of a measurable space denoted in these notes $\varXi$ and some [[Measure\|measure]] denoted $\psi$. It is written as:
$$
(\varOmega, \varXi, \psi)
$$
We require that $\psi(\varOmega)$ is well defined:
- if $\psi(\varOmega) < \infty$ then $\psi$ is a finite measure.
- if $\psi(\varOmega) = \infty$, then $\psi$ is an infinite measure
- if $\psi(\varOmega) = 1$, then $\psi$ is a **[[1. Cosmos/Probability Measure\|Probability Measure]]** (yessir!)

In the last case, we denote $\psi$ with a capital $\mathbb P$. 

So we can denote it ($\varOmega, \varXi, \mathbb P$) or say that $\mathbb P$ is a probability measure on the [[Measurable Space\|measurable space]] ($\varOmega, \varXi$)!
### So the measure axioms applied to Probabilities
1. $\mathbb P(\varnothing) = 0$
2. $\mathbb P(\varOmega) = 1$
3. If $A_1, A_2, \dots$ are disjoint $\varXi-$measurable sets, then
   $\mathbb P(\bigcup_{i=1}^{\infty} A_i) = \sum_{i=1}^{\infty} \mathbb P(A_i) \le 1$

So as we see we can define a probability space which is nothing more than a measurable space where the measure is a probability measure space is $(\varOmega, \varXi, \mathbb P)$.

From now on, I'll denote the probability measure as $P$. From this, we can now define [[Event\|events]] rigorously. They are nothing more than the $\varXi-$measurable sets of our probability measure space. 

This now answers why we specified "subsets under consideration" if a subset is not in our $\varXi-$algebra, then the measure defined on our [[Measurable Space\|measurable space]] does not consider it. Therefore it does not have a probability.
### The Magic
There is absolutely no prescriptions (or right way) as to how to define a [[1. Cosmos/Probability Measure\|Probability Measure]] or the $\sigma-$algebra for that matter.

Any arbitrary such space you can cook up, as long as you ensure it has the aforementioned properties is a totally valid probability measure. This give us a really expansible and rich soil to construct our [[Probability Theory\|Probability Theory]].

## References
[Probability Spaces 1](https://youtu.be/-nnJQ0kJgIY?si=u6RRL1dlwST7okND)
[Probability Spaces 2](https://www.youtube.com/watch?v=qVlD7K7ZJm8&list=PLbMVogVj5nJQqGHrpAloTec_lOKsG-foc&index=5)