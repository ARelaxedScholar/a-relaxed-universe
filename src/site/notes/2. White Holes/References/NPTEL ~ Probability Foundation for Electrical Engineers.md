---
{"dg-publish":true,"permalink":"/2-white-holes/references/nptel-probability-foundation-for-electrical-engineers/"}
---

202405201148
Status: #idea
Tags: [[Probability\|Probability]]
# NPTEL ~  Probability Foundation for Electrical Engineers
## Lecture 1
He briefly introduces the concepts and what will be covered. He then shows an interesting paradox that is solved by the fact that while the English question is the same for all, the mathematical question is different since for each solution we changed the [[Sample Space\|Sample Space]] in subtle ways.

In so doing, he "mata a dos parajos con un tira" (kill two birds with one stone) by showing the importance of rigorous probability definitions, and showing the importance of always planting a problem properly (and to ensure the Sample Space is clear to everyone.)

## Lecture 2-3
I skipped them. I am already familiar with cardinality and countability.

[[Cardinality\|Cardinality]]
[[Countability\|Countability]]
## Lecture 4
We embark on the journey of defining probability spaces and the basics of probability theory as we know it. This is a crucial lecture since he sets up the building blocks of probability theory. He defines things such as [[Random Experiment\|random experiments]], [[Outcome\|outcomes]], [[Event\|events]] and try to give a coherent picture of whole.
[[1. Cosmos/Probability Spaces#The Saviour of Algebra The $ sigma-$Algebra\|Probability Spaces (Start)]]

## Lecture 5
This is more of the same foundational work. Here among other things he introduces the concept of [[Algebra\|algebras]] and $\sigma-$algebras. He explain what the hell measures are, and why we should care. By the end of this lecture, I felt like "okay, I can see where this is going and I like it."
[[1. Cosmos/Probability Spaces\|Probability Spaces (Next)]]

## Lecture 6
In this part we define probability measure. Now that we've done all the heavy lifting in the prior part defining probability spaces, and touching on [[Measure Theory\|Measure Theory]], we can now reap the rewards. In this lecture we focus on what exactly the above definitions mean for our understanding of probability, and derive well-known results from them. We are now computing probabilities.
[[1. Cosmos/Probability Measure\|Probability Measure]]
## Lecture 7
[[1. Cosmos/Discrete Probability Spaces\|Discrete Probability Spaces]]

He also goes during the latter part of the video on uncountable sample spaces and how we can attempt to define probability measures on them. He observes first that. That there is no way in hell we can assign a probability to all events over that sample space. After all, if the space is uncountable, then by theorem it's power set will have a bigger cardinality. 

Even assuming there was somehow a way to assign a probability to all singleton measurable sets over a given sample set, all our formulas like:
$$
P(\bigcup_{i=1}^\infty A_i) = \sum_{i=1}^\infty A_i
$$
only hold hold for countably infinity, here the manifold is too complex to be sailed. 

He starts by trying to define the simplest and most intuitive probability distribution, the [[Uniform Distribution\|Uniform Distribution]]. Say I have an interval from $0$ to $1$ can I perhaps assign a probability to each point? No I cannot, no matter how small I choose due to the space being uncountable there will always be gaps between those values I have assigned probabilities to. Worse, they'll blow up to $\infty$.

He then compromises and says, well that doesn't work. Let us give probabilities to sections of the sample space instead. I'd want my probability to be given by the difference between end points and my probability to be the proportion of the section under consideration and the length of the interval (so $1$). That's a step forward, a leap even.

We derive from there that we need the following properties:
$$
P([a,b]) = P([a,b)) = P((a,b)) = P((a,b))
$$
So the endpoints are inconsequential.

Also 
$$
P([a,b]) = P([a+x,b+x])
$$
Assuming that adding $x$ does not push us out of the sample space, we are saying that if the proportion of the length of that section to the full length is the same, they are the same no matter their probabilities.

Cool, let's go! 

Except no. Because we can show by contradiction that if the $\sigma-$algebra under consideration is $2^\varOmega$, there is no probability measure that will hold the aforementioned two properties. 
Therefore we cannot compute continuous intervals *cue sad trumpet noises.*

At least that was until a group of geniuses in the 20th century unearthed modern measure theory and gave us the [[Borel Sets\|Borel Sets]] and [[Borel-Sigma Algebras\|Borel-Sigma Algebras]]. These things are the solution to our conundrum. Sadly we lose the richness of the sample space and must focus ourselves on a subset of the power set of $\varOmega$ that is *Borel*. But we now gain the ability to do probability measures on uncountably infinite sample spaces. Yay!

This where we stop for the 20th of May. I am happy. Today was a good day.
## References
