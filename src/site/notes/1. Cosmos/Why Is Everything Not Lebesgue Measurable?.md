---
{"dg-publish":true,"permalink":"/1-cosmos/why-is-everything-not-lebesgue-measurable/"}
---

202405240900
Status: #idea
Tags: 
State: #nascient
# Why Is Everything Not Lebesgue Measurable?

## The Intuition
Fundamentally, the crux of the proof lies on the fact that in a uniform measure, we require the property of translation independence. Which means that some space on the $(0,1]$ interval, no matter how trifling will always represent the same probability which is an issue because no matter how small you make that probability, considering the fact there are uncountably many such intervals in the space at hand, its associated measure will explode to $\infty$.

One example is the following:
$\mu((0.1,.9])=.8$ 
then
$\mu((0.11,.99])=.8$
as well since I just translated the space by $.01$
and you can convince yourself that I can do that infinitely many times.

This is not quite the issue though, because in the above situation we have overlapping sets therefore countable additivity wouldn't apply. But through the use of [[Equivalence Classes\|Equivalence Classes]] and more specifically through the use of an equivalence relation that makes two things equivalent if they have the same rational modulo, it becomes possible to manufacture a situation where we have uncountably many equivalence classes which cover the gamut of possible values in the space in such a way that the countable additivity axiom is actually usable.

Then either we assign a measure to those tiny slivers that is $0$, in which case we obtain $P(\varOmega)=0$, or we give them a value $\varepsilon$ in which case, no matter how tiny that value is, since it is positive (by definition of a measure), it will explode to $\infty$.

## The Proof

## How To Circumvent that Issue?
- [[Say bye-bye to the Axiom of Choice\|Say bye-bye to the Axiom of Choice]]
- [[Replace countable additivity with finite additivity\|Replace countable additivity with finite additivity]]
- [[Restrict yourself to smaller sets\|Restrict yourself to smaller sets]]
In modern probability we pretty much invariably do the last one, through the use of [[1. Cosmos/Borel-Sigma Algebras\|Borel-Sigma Algebras]]. But other situations exist. There is an [[Axiom of Determinacy\|Axiom of Determinacy]] which states that if we are ready to reexamine our axioms, all sets are Lebesgue measurable.
## References
[The Banach-Tarski Paradox and Why Not Everything Is Lebesgue](https://www.youtube.com/watch?v=172m7qVy_FQ&list=PLrb6X_RiBI94b6dzCx-QwM-r0aZpJyPxS)