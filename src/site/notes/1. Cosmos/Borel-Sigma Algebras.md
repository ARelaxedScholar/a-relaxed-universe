---
{"dg-publish":true,"permalink":"/1-cosmos/borel-sigma-algebras/"}
---

 202405211429
Status: #idea
Tags: [[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]], [[Probability\|Probability]]
# Borel-Sigma Algebras
## Preamble
If we set a collection of subsets of $\varOmega$ (which does not have to be a $\sigma-$algebra) we know that [[There Always Exist A Smallest Sigma-Algebra That Contains Any Arbitrary Collection C\|There Always Exist A Smallest Sigma-Algebra That Contains Any Arbitrary Collection C]] since we can always find the set of all $\sigma-$algebras which contain our collection $C$ and then define that smallest $\sigma-$algebra as follows. Let us define $\digamma$ as the collection of all $\sigma-$algebras which contain $C$ (this collection is never empty since $2^\varOmega$ is one such $\sigma-$algebra) then:
$$
\sigma(C) = \bigcap_{\varXi\in\digamma} \varXi
$$

*Be careful to not confuse this with the idea of the $\limsup \digamma$ where $\digamma$ is the set of all those $\sigma-$algebra which contain our collection $C$ will be the smallest $\sigma-$algebra containing our $C$. While they look similar since $\digamma$ here is a collection of potentially uncountable sets rather than a sequence, the notion of limits does not apply here.*

We know intuitively that $\sigma(C)$ is the smallest $\sigma-$algebra which contains our collection $C$ since by definition:
- It is the intersection of $\digamma$ a set defined of all $\sigma-$algebras which contain $C$, (therefore $C$ is definitely in that intersection)
- [[1. Cosmos/The Countable Intersection of Sigma-Algebras is Always A Sigma-Algebra\|The Countable Intersection of Sigma-Algebras is Always A Sigma-Algebra]]

This is why we can be so brazen in defining our $\sigma(C)$ as the intersection of all those $\sigma-$algebras.

## So, Borel-$\sigma$ Algebras?
Let $\varOmega$ is a [[Topological Space\|Topological Space]], or $\varOmega$ is a [[Metric Space\|Metric Space]] or if you have no idea what those two (yet) as do I, then let $\varOmega$ be some subset of $\mathbb R^n$.

All we need is the concept of [[Open Sets\|Open Sets]].

Then a Borel set denoted $\mathscr B(\varOmega)$ is a $\sigma-$algebra generated by the open sets and that is defined by the space on which we are operating. In other words $\mathscr B(\varOmega) := \sigma(C)$ are one and the same, except that $C$ here is not an arbitrary collection but rather is specifically the set of all open sets in the topological space we are interested in. It is **the smallest $\sigma-$algebra containing all open intervals.** 

This is amazing because the $\mathscr B(\varOmega)$ contains just enough complexity for us to be able to do any measure of analysis without worries *pun-intended*, while possessing all the properties required for us to be able to use [[1. Cosmos/Lebesgue Measures\|Lebesgue Measures]] on it. Therefore it has just the right amount of complexity to allow us to base our [[1. Cosmos/Probability Theory\|Probability Theory]] without worrying.

In fact, the concept of Borel$-\sigma-$algebras gives us a space so rich, that unless you actively attempt to construct a non-Borel set, all sets you will encounter naturally in your adventures with probability with naturally be [[1. Cosmos/Borel Sets\|Borel Sets]]. This is why we all learn how to compute integrals on [[Probability Density Functions\|Probability Density Functions]] which is really just a kind of [[1. Cosmos/Lebesgue Measures\|Lebesgue measure]] without ever learning what a [[1. Cosmos/Borel Sets\|Borel set]] is. 

We do lose in a sense some of the richness of our [[1. Cosmos/Sample Space\|Sample Space]], but as a counterpart we gain interpretability and have a space that can actually be conquered, moreover we totally side-step paradoxes like the [[Banach-Tarski Paradox\|Banach-Tarski Paradox]].

## Continuous Probability Spaces
This concept is of direct interest in [[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]]. In a similar fashion to how in [[1. Cosmos/Discrete Probability Spaces\|Discrete Probability Spaces]] our defacto $\sigma-$algebra will be the power set of our sample space denoted $2^\varOmega$, in [[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]] the defacto $\sigma-$algebra will be the $\mathscr B(\varOmega$) which we often just denote $\mathscr B$ since its understood we are operating over the topological space represented by our sample space.

Therefore we have successfully standardized [[1. Cosmos/Probability Theory\|Probability Theory]] and can now start thinking about how to define [[1. Cosmos/Probability Measure\|probability measures]] in continuous spaces! Spoiler, we will abuse [[1. Cosmos/Lebesgue Measures\|Lebesgue measures]].


## References
[Borel Sets](https://www.youtube.com/watch?v=z5m6HXKx0Wo)
[Borel Sets and Lebesgue Measure](https://www.youtube.com/watch?v=z7-OerO97Cs&list=PLbMVogVj5nJQqGHrpAloTec_lOKsG-foc&index=9)