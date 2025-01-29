---
{"dg-publish":true,"permalink":"/1-cosmos/measurable-maps/","created":"2025-01-22T11:17:13.981-05:00","updated":"2024-05-23T22:00:06.316-04:00"}
---

202405232128
Status: #idea
Tags: [[Measure Theory\|Measure Theory]]
# Measurable Maps
Say we have two spaces $\varOmega_1$ and $\varOmega_2$, both equipped with a $\sigma-algebra$. In other words we need two [[1. Cosmos/Measurable Space\|measurable spaces]].

It is possible to define a map from $\varOmega_1$ to $\varOmega_2$ by the intermediary of their respective $\sigma-$algebras!

So we say that a map is measurable if for any element in $\mathscr A_2$ where ($\mathscr A$ is the $\sigma-$algebra in $\varOmega_2$), its pre-image is in $\mathscr A_1$.

Essentially we define a map as follows:
$$
f: \varOmega_1 \to \varOmega_2
$$
We say that the function is measurable is $f^{-1}(A_2)\in \mathscr A_1$ for all values $A_2$ in $\mathscr A_2$.
So, in other words the function is said to be measurable if when we take the value of the inverse of the function of a measurable set, the set obtained is still measurable.

A classic example of measurable maps is [[1. Cosmos/Indicator Functions\|Indicator Functions]].
## Why that weird definition in terms of inverse?
It's due to how they are used in application rather than from intrinsic properties of measurable spaces and what not.

Generally when trying to solve a problem, and that you have a map you will be working in another dimension. You can see it as an adventurer stepping into a portal. Once on the other side of that portal, the things that you can do are already forced upon you in the sense that you can only measure things that are measurable. Therefore there is no need to make that a property of the definition. However, if you are doing work in that world, at some point you'll want to go back home for further analysis. In such a case it'd be silly if the object that you could perfectly measure in one dimension is now dead weight in your own dimension. 

The intuition is similar here. If there's a set of interest in $\varOmega_2$, for it to have been of interest it had to have been in $\mathscr A_2$, else you couldn't have worked with it. But if we want to see how it relates to the space $\varOmega_1$, we will need the preimage of that set to also be measurable.

## Why Do We Care?
Besides what is clear from the need to be able to analyze sets across multiple dimensions, it is a crucial notion in [[Integration Theory\|Integration Theory]] especially when it comes to [[Lebesgue Integrals\|Lebesgue Integrals]].
## References
[Measurable Maps](https://www.youtube.com/watch?v=11heoNVavvM&list=PLBh2i93oe2qvMVqAzsX1Kuv6-4fjazZ8j&index=5)