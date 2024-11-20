---
{"dg-publish":true,"permalink":"/1-cosmos/algebra/","created":"2024-08-31T23:47:13.569-04:00","updated":"2024-05-29T12:01:25.556-04:00"}
---

202405240847
Status: #idea
Tags: [[Measure Theory\|Measure Theory]]
State: #nascient
# Algebra

A collection of subsets $\varUpsilon$ of a sample space $\varOmega$ such that:
- $\varnothing$ is in the set (since it's the complement of $\varOmega$)
- If $A$ is in the set $\varUpsilon$, then $\omega^c$ is in the set as well
- If $A$ and $B$ are in the set $\varUpsilon$, so is $A \cup B$.

If all three of these conditions holds, we have an [[1. Cosmos/Algebra\|algebra]].
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
The issue is that this is an infinite intersection. Which under our current rules no matter the algebra we make, no algebra can guarantee that this event will be in it (even if all the individual events are.) This is a huge problem since everything else, be it [[1. Cosmos/Probability Measure (According to Kolmogorov)\|probability measure]], the definition of [[Probability\|probability]] itself and whatnot will be based on the assumption that our workbench contains all there is to consider.

In fact any event that would be represented as some elementary operation on an infinite number of sets would have the same problem. Since we have no guarantee it would be in any algebra, it could happen to be (after all $\varOmega$ is) but we cannot be certain ever.

## References
