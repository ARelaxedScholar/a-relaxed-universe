---
{"dg-publish":true,"permalink":"/1-cosmos/probability-measure/"}
---

202405201744
Status: #idea
Tags: [[Probability\|Probability]]
# Probability Measure
A Probability measure is a special type of measure which maps elements from a $\sigma-$algebra to the interval $[0,1]$. That is really it.

It has the same properties as you would expect for a standard measure:
- $P(\varnothing)=0$
- If $A_1, A_2, \dots$ are disjoint then $P(\bigcup_{i=1}^\infty A_i) = \sum_{i=1}^\infty P(A_i)$


## Properties of Probability Measures
### Formula for Complement
But from that we can derive everything we come to know about probability.
For example, since we know that $P(\varOmega)$ (where $\varOmega$ is the sample space) is $1$, and we know that for any set $A$, $A \cup A^c = \varOmega$ and $A \cap A^c = \varnothing$, we can use the second axiom of measures to say to derive this well-known fact:
$$
\begin{align}
\varOmega &= A \cup A^c \\
P(\varOmega) &= P(A \cup A^c)\text{, using both sides as inputs to the probability measure P}\\
P(\varOmega) &= P(A) + P(A^c) \text{, by second axiom}\\
1 &= P(A) + P(A^c) \text{, by definition of a probability measure}\\
P(A^c) &= 1-P(A)

\end{align}
$$

You can also prove easily that $A \subseteq B$, then $P(A) \le P(B)$, we leave that as an exercise to the reader. Lel.

Using [[Measure Theory\|Measure Theory]] as the foundation of [[Probability Theory\|Probability Theory]] makes all the other derivations similarly beautiful.
### Formula for unions : The Inclusion-Exclusion Principle
Let's first start by proving the following $P(A \cup B) = P(A) + P(B) - P(A \cap B)$,
This is my derivation of it.
$$
\begin{align}
A \cup B &= (A \setminus B) \cup B \text{, we rewrite the LHS in a more convenient fashion} \\
P(A \cup B) &= P(A \setminus B \cup B\\
&= P(A \setminus B) + P(B) \text{, by second axiom}\\
&= P(A\cap B^c) + P(B)\\
&= P(A)-P(A\cap B)+P(B) \text{, since }A \setminus B \text{ is the part of }A \text{that is not in } B\\
&= P(A)+P(B)-P(A \cap B) \text{, simple rearrangement}
\end{align}
$$
Boom!
This gives us the rigorous proof for why this equality holds, now what is the general form of the formula? What if instead of $A$ and $B$, we have $A_1, A_2, A_3, \dots, A_n$ which are all in our $\sigma-$algebra.

What is the formula for $P(\bigcup_{i=1}^n A_i)$?
![Pasted image 20240520183722.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240520183722.png) 
*screencap from Wikipedia cause I ain't typing allat.*

### How to Prove it?
- Induction
- Indicator Variables and Expectation
I did the latter for an assignment, for the former... well good luck with that.

### Continuity of Probability Measures
If $A_1, A_2, \dots \in \sigma\text{-algebra } \varXi$ then,
$$
P(\bigcup_{i=1}^\infty A_i) = \lim_{m \rightarrow \infty} P[\bigcup_{i=1}^m A_i)]
$$
This looks rather obvious (I mean it looks really similar to how we definite infinite summations,) but there's actually more to this statement than meets the eye. This is a really important theorem that is used all the time in [[Probability Theory\|Probability Theory]]. Also, among other things we are **NOT** taking the limit inside the brackets, an actual rigorous proof is required to show the equivalency.

Also $\bigcup$ shouldn't be seen as a sequential operator which operates $A_1$ and $A_2$, and then $A_1\cup A_2$ and $A_3$, etc. Instead it takes everything at once. While the following statement is true
$$
\bigcup_{i=1}^\infty A_i = \lim_{m \rightarrow \infty} (\bigcup_{i=1}^m A_i) $$
(this limit refers to increasing inclusions of sets) it is not wise to move the limits in or out.

Indeed, one should be careful when introducing limits in a [[Measure Theory\|Measure Theory]] context, especially when it comes to bringing a limit in and out of a measure. Unless there's a specific argument to support it, or a convergence theorem that says we can, one should not assume it is correct to do so.

A proof of this theorem can be found on YouTube, the second link in the references covers it during the lecture.

#### Corollary
##### 1. 
If $A_1 \subseteq A_2 \subseteq A_3 \subset \dots$
Then by the previous result:
$$
P(\bigcup_{i=1}^\infty A_i) = \lim_{m \rightarrow \infty} P(A_m)
$$
##### 2.
If $A_1 \supseteq A_2 \supseteq A_3 \supseteq \dots$
Then by previous result and DeMorgan's:
$$
P(\bigcap_{i=1}^\infty A_i) = \lim_{m \rightarrow \infty} P(A_m)
$$
This is not a typo, in fact it makes perfect sense. If I keep taking intersections of a sequence of set which are non-increasing (in the sense that $A_i \supseteq A_j$ for all $i,j$ where $i<j$), then at the end of the infinite road, the one set that will be in all of them is $A_m$.  

Observation, we see that if the sequence is non-increasing, or non-decreasing the limit of an infinite sequence of set will simply be $\lim_{m \rightarrow \infty} P(A_m)$.

### Union-Bound Property
Let $A_1, A_2, \dots$ all be events, then:
$$
P(\bigcup_{n=1}^\infty A_i) \le \sum_{i=1}^\infty P(A_i)
$$

Intuitively, if all the $A_i$ are disjoint, then by the second axiom we have equality, but if even one pair $A_i$, $A_j$ overlaps, we will double count their intersections. This problem will compound the more pairs that overlaps exist.

This can be proven pretty neatly using [[Indicator Variables\|Indicator Variables]], but it can be also shown directly using the $A_i$ to $B_i$ transformation that is used to show the *continuity of probability measures*. The second link of references is really useful for understanding all of that.
## References
[[1. Cosmos/Probability Spaces\|Probability Spaces]]
[Probability Measures Lecture](https://www.youtube.com/watch?v=A8tHxhJfwkA&list=PLbMVogVj5nJQqGHrpAloTec_lOKsG-foc&index=6)