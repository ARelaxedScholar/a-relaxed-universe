---
{"dg-publish":true,"permalink":"/1-cosmos/lebesgue-measures/"}
---

202405211626
Status: #idea
Tags: [[Measure Theory\|Measure Theory]]
# Lebesgue Measures
A Lebesgue measure is a type of [[1. Cosmos/Measure\|measure]] defined on a continuous sample space $\varOmega$ and more specifically on the Borel set $\mathscr B$ associated with that sample space, effectively giving us a concept of "length", "area" or "volume" thus a "measure" over that [[Topological Space\|topological space]]. 

*Note the first usage of measure is the idea of a function from $\sigma-$algebra to $[0,\infty]$ the second use of measure (between quotation marks) represents the idea of intuitive notion measure used in the real world.*

## Properties of Lebesgue Measures
The motivation is that we wanted to define measures on the reals $\mathbb R$ and whatnot in a rigorous way. For those measures, for those "standardization of volume" to make sense, we require these two properties:
- $\mu([a,b])=b-a, b>a$
- $\mu(x+A)=\mu(A)$, for all $A \in 2^\mathbb{R}$ and $x \in \mathbb R$

The first property tells us that the Lebesgue measure gives us the length of an interval for any arbitrary interval $[a,b]$.
The second property tells us that $\mu([10,12])=\mu(0,2)=\mu(2,4)$ because while the numbers are different they all have the same length. The length of the measure is invariant no matter where it is taken.

The catch is that [[We Cannot Define a Lebesgue Measure on Power Set of a Uncountably Infinite Sample Space\|We Cannot Define a Lebesgue Measure on Power Set of a Uncountably Infinite Sample Space]]. Which stumped measure theorists for a while, this in fact lead to the invention of a whole new measure theory centralized around the idea of [[1. Cosmos/Borel-Sigma Algebras\|Borel-Sigma Algebras]].


## Why Can't Lebesgue Measures be defined on the whole power set $2^\varOmega$?
## Usage in [[Probability Theory\|Probability Theory]]
By using the standard and more easily manipulable concept of [[Algebra\|algebras]] we can surgically select elements of $2^\varOmega$ that are of interest to us and assign them probabilities. These probabilities since assigned on algebras that are not $\sigma$ can hardly be called [[1. Cosmos/Probability Measure\|probability measures]] and are typically denoted $P_0$. For the uniform case for example our pseudo-measure $P_0$ is for an arbitrary algebra $\varXi$ is:
$$
P_0(\varXi) = \sum_{i=1}^n(b_i-a_i)
$$
to which we add the specification that:
$$
P_0(\varnothing) = 0
$$

This is well and all, except that probabilities do not work well on [[Algebra\|general algebras]] more specifically, the concept of closure under countable unions is a crucial one to allow any meaningful analysis of probabilities.

This is where we stand on the shoulders of giants and invoke the [[1. Cosmos/Caratheodarry's Extension Theorem\|Caratheodarry's Extension Theorem]] by which we know that if our pseudo-measure 
- assigned a probability to $\varOmega$ of $1$
- and was countably additive (for the cases where the countable union actually is in the algebra)
then there exists an [[1. Cosmos/Probability Measure\|actual measure]] that agrees with our pseudo-measure for all the measures, and not only that, that it extends to a $\sigma-$algebra (which typically will be the $\mathscr B$).

Yes, you've guessed it: that measure is called the [[1. Cosmos/Lebesgue Measures\|Lebesgue measure]].

Note that the Lebesgue measures are by no means restricted to probability spaces and are a really important concept in [[Measure Theory\|Measure Theory]]. But for [[Probability Theory\|Probability Theory]] which is not much more than a special case of the latter, they play a pivotal role in allowing us to analyze [[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]].

Note, that based on the above we can show that for any singleton set element of our $\sigma-$algebra the probability will be $0$.

### Weird Stuff and Considerations
What is the probability of $P(\mathbb Q \cap \varOmega)$.
This is really weird, but while there is an infinity of rational numbers $\mathbb Q$ in $\varOmega$, we know that all singleton element has probability $0$. Since all these singleton elements by definition contain only one element, and they are all distinct, it follows that all of those probability measures are individually equal to $0$. Then by countable additivity we have $0$.

Thus as counter-intuitive as this might seem, if I throw a dart and I have a uniform chance of reaching any individual number on that then the probability of my number landing on a rational number is mathematically $0$.

More then that, it is not approximately $0$, or $0$ in some sense--it is exactly $0$.

This leads to the observation that $P(A)=0$ does not mean that $A$ never occurs, it simply means that its probability is $0$.

(Observe that since $P(\mathbb Q \cap \varOmega) = 1$ since irrational numbers are the complement of rational numbers, it follows that $P([\mathbb R \setminus \mathbb Q] \cap \varOmega) = 1)$ even though both sets are non-empty. The intuition is that if I throw a dart, I am almost guaranteed to land on a irrational number, and it really unlikely that I will land on a rational number. But the former **COULD** occur!)

In a [[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]] an event with a probability of $0$ could still occur, but it is not expected to occur--not likely to occur in a probabilistic sense. Note that this notion of "expected to occur" is unrelated to the probabilistic notion of [[1. Cosmos/Expected Value\|Expected Value]].

Observe that the weirdness goes further, while $P(\varOmega)$ has a probability of $1$, for literally any of the uncountably-many-individual elements in the interval its probability is $0$. This is a reflection of how in [[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]], probability measures "length" which is then likened to an esoteric sense of likeliness.

This is another example of the disconnect between everyday language and mathematics.

This is a feature and not a bug of [[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]], it is with humour that we say that in continuous probability spaces $0$-probability events occur all the time, in a sense (at the highest level of resolution) they are the only thing that can occur.

Spoiler, the only impossible event is $\varnothing$. Informally, an [[Impossible Event\|Impossible Event]] is an event that does not contain any of the possible [[Outcome\|outcomes]] of a [[Random Experiment\|random experiment]].

Refer to this for a more in-depth comparison: [[Impossible Event vs 0-Probability Events\|Impossible Event vs 0-Probability Events]]

This tells us two things
- Be careful of "real-world intuition" the deeper you go into mathematics
- Infinity does not in any way guarantee a positive measure, in fact [[The Cantor Set has A Probability Measure of 0\|The Cantor Set has A Probability Measure of 0]]. This is meaningful because the [[Cantor Set\|Cantor Set]] is not only infinite, it is uncountably infinite.



## References
