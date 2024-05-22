---
{"dg-publish":true,"permalink":"/1-cosmos/discrete-probability-spaces/"}
---

dg-publish: true
202405201927
Status: #idea
Tags: [[Probability\|Probability]], [[2. White Holes/References/NPTEL ~ Probability Foundation for Electrical Engineers\|NPTEL ~ Probability Foundation for Electrical Engineers]]
# Discrete Probability Spaces
When we are dealing with a countable [[Sample Space\|Sample Space]] $\varOmega$, then we will be operating in the realm of discrete probability spaces. $\varOmega$ could be infinite or finite.

They are nice because they are simple and intuitive to work with.

When dealing with those cases, it is possible to assign a probability to all elements of the sample space since $2^\varOmega$ will be a countable set. Thanks to that all subsets of $\varOmega$ are events, and therefore we can assign a probability to any element of $\varOmega$. Therefore in discrete contexts, our [[1. Cosmos/Probability Spaces\|Probability Spaces]] will defacto be defined as follows $(\varOmega, 2^\varOmega)$ because **WE CAN** preserve the full richness of the space, we can make analysis as granular as we want, and therefore **WE DO**.

In the context of [[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]], we resort to [[1. Cosmos/Borel Sets\|Borel Sets]] and [[1. Cosmos/Lebesgue Measures\|Lebesgue Measures]] because we have to, not because we want to. After all keep in mind that the sample space represents the set of outcomes relevant to our target, why would we choose to drop valuable data if we do not have to? Exactly, we don't.

So, how do we accomplish this witchcraft?

By assigning probabilities to singleton elements (subsets containing single elements of the sample space) in such a way that:
$$
\sum_{x\in\varOmega} P(\{x\}) = 1 
$$
In such an environment, what is $P({x_1, x_2, x_3})$? Well it is $P({x_1})+P({x_2})+P({x_3})$. 

Note that these probabilities can be assigned as haphazardly as we want, I could make a bunch of $x_i$ have probability $0$ and give all the probability bandwidth to some arbitrary $x_\alpha$, or I could weight it in such a way that the bigger the index of $x_i$ is, the greater its assigned probability. 

As long as it all sum to $1$ in the end, we are gucci.

In practice, unless there's a reason to do otherwise (will vary based on [[Random Experiment\|Random Experiment]]), we generally assume a [[Uniform Distribution\|Uniform Distribution]], but this is by no mean an obligation. 

## Probability Mass Functions (PMF)
Recall how in measure theory a measure is nothing more than a function that maps elements of our $\sigma-$algebra (in this case the power set of $\varOmega$) to the space $[0,1]$.

A [[Probability Mass Function\|Probability Mass Function]] based on the theory covered in [[1. Cosmos/Probability Spaces\|Probability Spaces]], is nothing more than the measure that maps those singleton subsets of the $\sigma-$algebra to the right values. We interpret this measure as the likelihood of our random experiment to yield a given event.

This is the name we give to a [[Probability Density Functions\|Probability Density Functions]] when operating in a discrete probability space.

### Important Consideration
While at times due to how we write things, we can mistakenly think that we are assigning probabilities to elements of the [[Sample Space\|Sample Space]]. This is categorically false. While an harmless error most of the time (and in fact the way everyone that doesn't learn the foundations of probability learns it,) probability are assigned to elements of the $\sigma-$algebra, not to element of $\varOmega$. This might sound like a nitpick, but its not.

While not too big of an issue in [[1. Cosmos/Discrete Probability Spaces\|Discrete Probability Spaces]], it is crucial to understand that when we go to [[1. Cosmos/Continuous Probability Spaces\|Continuous Probability Spaces]], because in the latter it is generally not possible to assign a probability to all subsets of $\varOmega$ and therefore all we can do is treat with the $\sigma-$algebra and its [[Measurable Sets\|measurable sets]].

This is true in the discrete case as well! But that subtlety can be missed if we're not careful.
## References
[Lecture 7](https://www.youtube.com/watch?v=PseYlBGV_00&list=PLbMVogVj5nJQqGHrpAloTec_lOKsG-foc&index=7)