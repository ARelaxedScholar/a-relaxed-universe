---
{"dg-publish":true,"permalink":"/2-white-holes/references/mat-3172-foundations-of-probability/"}
---

202405271904
Status: #reference
Tags: [[1. Cosmos/Probability Theory\|Probability Theory]] 
# MAT3172 ~ Foundations of Probability

> [!NOTE] Excerpt from [Catalogue MAT3172](https://catalogue.uottawa.ca/search/?P=MAT%203172)
> An overview of probability from a non-measure theoretic point of view. Random vectors; independence, conditional expectation and probability, consequences. Various types of convergence leading to proofs of the major theorems in classical probability theory. An introduction to simple stochastic processes such as Poisson and branching processes.

## Lecture 1
Professor Mahmoud Zarepour (great teacher by the way if you have the option to take him) starts with an introduction of set theory since it seems nothing serious can be done in math without some [[Set Theory\|Set Theory]]. 

He introduces the need for the rigorous Kolmogorov definition of probability that came as a way to unify a field that until now was quite disparate due to people working under subtly different assumptions, to solve agreed upon problems. As a result, contradictions would prop up and many problems would have different but properly reasoned answers.

In this video, he goes over the following points concluding with the concepts of [[Infimum\|$\inf$]] and [[Supremum\|$\sup$]] of both sequences and sets.
#### Lesson Points:
[[1. Cosmos/Outcome\|Outcome]]
[[1. Cosmos/Event\|Event]]
[[Set Theory\|Set Theory]]
[[1. Cosmos/Indicator Functions\|Indicator Functions]]
[[Limits of Sequences\|Limits of Sequences]]
[[1. Cosmos/Limits of Sets\|Limits of Sets]]



## Lecture 2
![Pasted image 20240528173802.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240528173802.png)
We start the lecture with the above screenshot which gives us a reminder of the essential facts. And sets the workbench for the remainder of the class.

We introduce the fact that for an increasing sequence of sets say $B_n$, it's limit will be $\bigcup^\infty B_n$
On the other side, if we have a decreasing sequence of sets say $D_n$, it's limit will be $\bigcup^\infty D_n$.

Here we motivate the use of [[1. Cosmos/Borel-Sigma Algebras\|Borel-Sigma Algebras]] for our definitions of probability. More specifically we introduce the [[Cantor Set\|Cantor Set]] and show how there are many weird sets that can be constructed on the $\mathbb R$ line that are not suitable for probability. While the [[Cantor Set\|Cantor Set]] itself is [[1. Cosmos/Borel Sets\|borel]] there are sets that can be constructed from it which are not [[1. Cosmos/Borel Sets\|Borel Sets]], and therefore sets we cannot define [[1. Cosmos/Lebesgue Measures\|Lebesgue Measures]] on (not yet introduced in this class.)

He also reassures us that while we've been doing [[Real Analysis\|Real Analysis]] and [[Calculus\|Calculus]] for these two lectures, and we will keep seeing to have a rigorous understanding of the theorems, we will be evaluated on our understanding of [[1. Cosmos/Probability Theory\|Probability Theory]] as it pertains to [[Probability\|Probability]].
### Lesson Points
[[1. Cosmos/Limits of Sets\|Limits of Sets]]
[[1. Cosmos/Borel-Sigma Algebras\|Borel-Sigma Algebras]]
[[1. Cosmos/Borel Sets\|Borel Sets]]
## Lecture 3
![Pasted image 20240529115323.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240529115323.png)
Here we start defining the notion of [[1. Cosmos/Probability Measure (According to Kolmogorov)\|probability measures]], and we start by conceiving them as set functions. This is a crucial reminder of the fact that we assign probabilities to [[Events\|events]] and not individual [[1. Cosmos/Outcome\|outcomes]]. 

We then spend the rest of the lecture defining probability measures (without really mentioning measure theory) both from the inherited version from [[Measure Theory\|Measure Theory]] and simple [[1. Cosmos/Measure\|measures]] and from the more "intuitive" interpretation of expected value. 

Really insightful class, and after having seen how some things like the formula for $P(\bigcup^{\infty}_{i=1} A_i)$ are proven using the standard Kolmogorov approach, the existence of a more intuitive approach that makes such proofs almost trivially simple is very welcome.
### Lesson Points:
[[1. Cosmos/Probability Measure (According to Kolmogorov)\|Probability Measure (According to Kolmogorov)]]
[[1. Cosmos/Probability Measure (Based on Expected Value)\|Probability Measure (Based on Expected Value)]]



## [Lecture 4](https://uottawa-ca.zoom.us/rec/play/rUhd_NJ8wUBaYfwhDNAWbYDZC5bjHQcZmvMEKnkgggHVV7J9cX8FWcXUpJ5HeSF-TlSLIRYBBYcKpy07.3Sj6BWtYawidueG4)
After defining the probability measures, we ignore them for a bit to return to limits and their usage. Starting with [[1. Cosmos/Fatou's Lemma\|Fatou's Lemma]]. We spend the first few minutes of the class going over it and explaining how it follows.

We then define independence of events.

It seems we define it only so that we can prove the [[1. Cosmos/Borel-Cantelli Lemma\|Borel-Cantelli Lemma]] right after. Honestly, considering this is a probability class, there are worse moments that Dr Zahrepour could have chose to present it, lmao.

Overall, this lecture focused on these points.

Lesson Points
[[1. Cosmos/Fatou's Lemma\|Fatou's Lemma]]
[[1. Cosmos/Event#Independence of Events\|Event#Independence of Events]]
[[1. Cosmos/Borel-Cantelli Lemma\|Borel-Cantelli Lemma]]


## [Lecture 5](https://uottawa-ca.zoom.us/rec/play/mM6nS1xG3DoHNmtWOjXjzPknUpfyatR3w8uzAG4ZZ1KKysssNFabh5Hl21HCniRa3ZhKzftOButTmKfb.263MPOfoiCr6RK-B)
After proving the [[1. Cosmos/Fatou's Lemma\|Fatou's Lemma]] which give us the ability to take the limit in and out of measures given the limit of a family of event $E_n$ **exists** and then proving the [[1. Cosmos/Borel-Cantelli Lemma\|Borel-Cantelli Lemma]] which gave us a way to say decisively if a given family of event $E_n$ did not occur infinitely many times (and under independence they did), we now start talking about what we typically think of when mentioning probability. [[1. Cosmos/Probability Mass Function\|Probability Mass Function]] and [[1. Cosmos/Probability Density Functions\|Probability Density Functions]], and how the heck do we measure a probability for arbitrary events?

This lecture does not break what we've learned before in older courses, but it re-contextualizes a lot of it and give us a more rigorous underpinning. Less rigorous than [[Measure Theory\|Measure Theory]], but rigorous enough for use.

### Lesson Points
[[1. Cosmos/Borel-Cantelli Lemma\|Borel-Cantelli Lemma]]
[[1. Cosmos/Random Variable\|Random Variable]]
[[1. Cosmos/Cumulative Density Function\|Cumulative Density Function]]
[[1. Cosmos/Riemann Integrals\|Riemann Integrals]]
[[1. Cosmos/Riemann-Stieltjes Integrals ~ Generalization of Riemann integrals\|Riemann-Stieltjes Integrals ~ Generalization of Riemann integrals]]
[[Lebesgue Integrals\|Lebesgue Integrals]]
[[1. Cosmos/Expected Value\|Expected Value]]
[[1. Cosmos/Probability Density Functions\|Probability Density Functions]]
[[1. Cosmos/Markov's Inequality\|Markov's Inequality]]
## [Lecture 6](https://uottawa-ca.zoom.us/rec/play/e0_qaNsXDdTF6sIKFhQMaQsMbq23BeKJxEGcKy0mrMHdSQoIAnIdSX9JQvFO4hgE8EZ7guNu2AffYc46.nNZpJVndPtN-GUyZ)
So we start where we left off last lecture with [[1. Cosmos/Markov's Inequality\|Markov's Inequality]]. 
From Lecture 6 and from there and then we start our journey into stating and proving inequalities. 

Besides inequalities galore, we introduce the concept of [[1. Cosmos/Moment Generating Function\|Moment Generating Function]] and we prove the moment generating functions for well known distributions like the [[Gamma Distribution\|Gamma Distribution]], and the [[Chi-Squared Distribution\|Chi-Squared Distribution]].

### Lesson Points
[[1. Cosmos/Markov's Inequality\|Markov's Inequality]]
[[1. Cosmos/Chebyshev's Inequality\|Chebyshev's Inequality]]
[[1. Cosmos/Cauchy-Schwarz's Inequality\|Cauchy-Schwarz's Inequality]]
[[1. Cosmos/Moment Generating Function\|Moment Generating Function]]
## [Lecture X-1](https://uottawa-ca.zoom.us/rec/play/pUy61bvkwQfcIHu7ZjbCAjwKJxlz1jlUj4NfoLlIMSRuXxfBzzpyOhGUcihUa1mXfRYDRuNhG7YAugXg.yVzkslX7ygR23W-O)
## [Lecture X (Latest)](https://uottawa-ca.zoom.us/rec/play/ga0_-VqTYW-18X1LjAO-c30lRpfoLFeolpYth9f2QPAU9EkJajzDqZNzF3GlTpvrSFtmBx0oOmLzc_rT.xOnU5mIkKNrE0PAl)
We start by reviewing [[1. Cosmos/Holder's Inequality\|Holder's Inequality]]
## References
[[1. Cosmos/MAT3172 ~ Flashcards\|MAT3172 ~ Flashcards]]
### Prerequisites (I took):
[[MAT2122 ~ Multivariable Calculus\|MAT2122 ~ Multivariable Calculus]]
[[MAT2341 ~ Introduction to Applied Linear Algebra\|MAT2341 ~ Introduction to Applied Linear Algebra]]
[[MAT2371 ~ Introduction to Probability\|MAT2371 ~ Introduction to Probability]]

