---
{"dg-publish":true,"permalink":"/1-cosmos/outcome/"}
---

202405281458
Status: #idea
Tags: [[1. Cosmos/Probability Spaces\|Probability Spaces]]
State: #nascient
# Outcome
An outcome for a given sample space $\varOmega$ is nothing more than some element of the sample space.

It is directly connected to the definition of our [[Random Experiment\|Random Experiment]] which tells us what exactly we are working under, and based on which we will define the things that are of interest. The same [[Random Experiment\|Random Experiment]] could have a totally different [[1. Cosmos/Sample Space\|sample spaces]] based on the details we choose to consider; which directly changes the set of possible outcomes (which is all the $\varOmega$ is.)

An outcome could belong to a continuous (uncountable) sample space *ie: $\mathbb R$ or $[0,1]$*

Or it could belong to a countably finite or infinite sample space (ie: $H, HH, HHH,...$ or $\{H,T\}$)
For the first example a possible random experiment would be I flip a coin until I encounter the first tail, only consider the heads. The second example could be I flip a coin once, what possible outcomes are there.

## Relation to Event
While outcomes and [[1. Cosmos/Event\|events]] are related, they are never the same. Indeed, an outcome is an element of the sample space, while an event is a **subset** of the sample space. The closest they could be to each other would be some outcome, and some set containing that outcome (referred to as a singleton set.) Observe that no matter what the outcome is we will be comparing something to a set containing that thing.

While this might seem pedantic this is an important distinction, indeed we **NEVER** assign probabilities to outcomes. Instead we assign them to events. In the discrete case we assign a probability to singleton sets of each outcome. 

Why is that important? Because an event by definition belong to a [[1. Cosmos/Sigma-Algebra\|$\sigma-$algebra]] which contains the subsets to which we can assign a measure. While in the discrete case the distinction and misunderstanding is not too problematic since our $\sigma-$algebra is just $2^\varOmega$, it becomes a stumbling block in the continuous case where we cannot take the power set of our sample space as an element and we need to be more careful about what "probability" even mean.
## References
