---
{"dg-publish":true,"permalink":"/2-white-holes/references/nptel-probability-foundation-for-electrical-engineers/","created":"2025-01-22T11:17:14.711-05:00","updated":"2024-05-29T12:01:27.153-04:00"}
---

202405201148
Status: #idea
Tags: [[Probability\|Probability]]
# NPTEL ~  Probability Foundation for Electrical Engineers

## Lecture 1 ~ An Introduction, why do we need rigorous probability?
He briefly introduces the concepts and what will be covered. He then shows an interesting paradox that is solved by the fact that while the English question is the same for all, the mathematical question is different since for each solution we changed the [[1. Cosmos/Sample Space\|Sample Space]] in subtle ways.

In so doing, he "mata a dos parajos con un tira" (kill two birds with one stone) by showing the importance of rigorous probability definitions, and showing the importance of always planting a problem properly (and to ensure the Sample Space is clear to everyone.)

#### Lesson Points:
[[Bertrand Paradox ~ Why Before Starting a Problem You Should Plant It Properly\|Bertrand Paradox ~ Why Before Starting a Problem You Should Plant It Properly]]
[[The Need for Rigorous Definition of Probability\|The Need for Rigorous Definition of Probability]]


## Lecture 2-3 ~ Stuff I skipped
I skipped them. I am already familiar with cardinality and countability.

[[Cardinality\|Cardinality]]
[[Countability\|Countability]]
## Lecture 4 ~ Probability Spaces (1)
We embark on the journey of defining probability spaces and the basics of probability theory as we know it. This is a crucial lecture since he sets up the building blocks of probability theory. He defines things such as [[Random Experiment\|random experiments]], [[1. Cosmos/Outcome\|outcomes]], [[1. Cosmos/Event\|events]] and try to give a coherent picture of whole.

#### Lesson Points:
[[1. Cosmos/Probability Spaces#The Saviour of Algebra The $ sigma-$Algebra\|Probability Spaces (Start)]]

## Lecture 5 ~ Probability Spaces (2)
This is more of the same foundational work. Here among other things he introduces the concept of [[1. Cosmos/Algebra\|algebras]] and $\sigma-$algebras. He explain what the hell measures are, and why we should care. By the end of this lecture, I felt like "okay, I can see where this is going and I like it."
#### Lesson Points:
[[1. Cosmos/Probability Spaces\|Probability Spaces (Next)]]

## Lecture 6 ~ Properties of Probability Measures
In this part we define probability measure. Now that we've done all the heavy lifting in the prior part defining probability spaces, and touching on [[Measure Theory\|Measure Theory]], we can now reap the rewards. In this lecture we focus on what exactly the above definitions mean for our understanding of probability, and derive well-known results from them. We are now computing probabilities.
#### Lesson Points:
[[1. Cosmos/Probability Measure (According to Kolmogorov)\|Probability Measure (According to Kolmogorov)]]
## Lecture 7 ~ Discrete Probability Spaces
Dr. Krishna starts by covering [[1. Cosmos/Discrete Probability Spaces\|Discrete Probability Spaces]] which are covered in their own notes.
Then he goes during the latter part of the video on uncountable sample spaces and how we can attempt to define probability measures on them. He observes first that. That there is no way in hell we can assign a probability to all events over that sample space. After all, if the space is uncountable, then by theorem it's power set will have a bigger cardinality. 

Even assuming there was somehow a way to assign a probability to all singleton measurable sets over a given sample set, all our formulas like:
$$
P(\bigcup_{i=1}^\infty A_i) = \sum_{i=1}^\infty A_i
$$
only hold hold for countably infinity, here the manifold is too complex to be sailed. 

He starts by trying to define the simplest and most intuitive probability distribution, the [[1. Cosmos/Uniform Distribution\|Uniform Distribution]]. Say I have an interval from $0$ to $1$ can I perhaps assign a probability to each point? No I cannot, no matter how small I choose due to the space being uncountable there will always be gaps between those values I have assigned probabilities to. Worse, they'll blow up to $\infty$.

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

At least that was until a group of geniuses in the 20th century unearthed modern measure theory and gave us the [[1. Cosmos/Borel Sets\|Borel Sets]] and [[1. Cosmos/Borel-Sigma Algebras\|Borel-Sigma Algebras]]. These things are the solution to our conundrum. Sadly we lose the richness of the sample space and must focus ourselves on a subset of the power set of $\varOmega$ that is *Borel*. But we now gain the ability to do probability measures on uncountably infinite sample spaces. Yay!

This where we stop for the 20th of May. I am happy. Today was a good day.

## Lecture 8 ~ Generated $\sigma-$algebra and Borel Sets
At the end of the last lecture Dr. Krishna stated a theorem that for uncountably infinite $\varOmega$, there was no way to map a probability measure to all of the subsets of that sample space. Therefore we need to first define a collection of subsets of that sample space that we definitely want to be able to measure, and then generate a $\sigma-$algebra that contains them.

But, any stupid one won't work. We want to generate the smallest $\sigma-$algebra that will contain the collections we care about? This is fundamentally what a [[1. Cosmos/Borel Sets\|Borel set]] is.

Why the smallest? Isn't that totally the opposite of what we attempted to do in the [[1. Cosmos/Discrete Probability Spaces\|Discrete Probability Spaces]]? Yes it is. My intuition for this which might be wrong, but that is my best attempt at it is that; we know for a fact (by theorem) that for uncountably infinite spaces it is not possible to define a probability measure for which we have both:
- resistance to translation so that two intervals of the same size have the same probability
- all intervals whether close or open have the same probability
That is we cannot define the simplest probability distribution ([[1. Cosmos/Uniform Distribution\|Uniform Distribution]]) on the power set of our $\varOmega$. This power set is simply too big. Taking the simplest and smallest $\sigma-$algebra that contains all of the sets that interest us (a [[1. Cosmos/Borel Sets\|Borel set]]) is an attempt at that.

We might fail to define a probability measure even on that, perhaps... Nah it won't happen thanks to [[1. Cosmos/Lebesgue Measures\|Lebesgue Measures]]. But we know that we can define measures on sets that are Borel, no such guarantees exist for bigger $\sigma-$algebras and considering bigger $\sigma-$algebras while it could be harmless could also lead to the inclusion of pathological sets to which we cannot assign as [[1. Cosmos/Lebesgue Measures\|Lebesgue measure]]--leading to probability-less events.

What do we mean by **smallest**? Simply if there's any $\sigma-$algebra which contains the subsets of elements $C$ that we want to consider, then the smallest such $\sigma-$algebra will be a subset of it. We know that there is always at least one $\sigma-$algebra that contains any arbitrary $C$ and that is $2^\varOmega$. Now

#### Lesson Points:
[[1. Cosmos/The Countable Intersection of Sigma-Algebras is Always A Sigma-Algebra\|The Countable Intersection of Sigma-Algebras is Always A Sigma-Algebra]]
[[There Always Exist A Smallest Sigma-Algebra That Contains Any Arbitrary Collection C\|There Always Exist A Smallest Sigma-Algebra That Contains Any Arbitrary Collection C]]
[[1. Cosmos/Borel Sets\|Borel Sets]]

## Lecture 9 ~ Borel Sets and Lebesgue Measures (1)
Let me spoil it, absolutely no concept of [[1. Cosmos/Lebesgue Measures\|Lebesgue Measures]] is talked here. Besides nuggets along the line like "we only assign measures to elements of the Borel set" or "the notion of length does not make sense for elements which are not in the Borel set" we don't even name drop the concept of [[1. Cosmos/Lebesgue Measures\|Lebesgue Measures]]. Instead we focus on reinforcing the idea of [[1. Cosmos/Borel Sets\|Borel Sets]] and how defining a [[1. Cosmos/Uniform Distribution\|Uniform Distribution]], more specifically defining the Uniform Probability Measure naturally leads to the invoking of [[1. Cosmos/Borel Sets\|Borel sets]] since when starting with the minimal collection of things of interest for a uniform distribution, and then taking the $\sigma$ "operator" on it, the $\sigma-$algebra we obtain can be proved to be naught more than the $\mathscr B(\varOmega)$ where $\varOmega$ is $(0,1]$.

This also made me realize that one reason why I love the lectures of Dr. Krishna so much is that he takes the time often to ask the class "How do we do that?", "How do you think we will proceed from here", and he is not afraid to expose the entire thing while still leaving some work for the student.

Furthermore, while he does do it from time to time, he uses the expression "this is easy", much less than other professors, therefore you do not feel stupid when watching him. Moreover when he does blurt those words, typically rewatching the last 5-10 minutes again or just pausing the video and thinking about it will lead the viewer to the same conclusion. Something which is not always true. I think I will create a note of [[How To Teach Effectively\|How To Teach Effectively]] where this will be a prominent point. [[How To Teach Effectively#Never Say This Is Easy.\|How To Teach Effectively#Never Say This Is Easy.]]

#### Lesson Points:
[[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]]



## Lecture 10 ~ The Lebesgue Measure : Standardizing the Concept of "Length"


#### Lesson Points:
[[1. Cosmos/Caratheodarry's Extension Theorem\|Caratheodarry's Extension Theorem]]
[[1. Cosmos/Lebesgue Measures\|Lebesgue Measures]]
## References
