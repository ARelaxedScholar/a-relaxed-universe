---
{"dg-publish":true,"permalink":"/1-cosmos/curse-of-dimensionality/","created":"2024-11-26T15:20:05.946-05:00","updated":"2024-11-26T15:41:53.794-05:00"}
---

202411261520
Status: #idea
Tags: 
State: #nascient
# Curse of Dimensionality

With a name that cool it almost makes you want it, except not really, cause it makes training models a pain.

The curse of dimensionality is what happens when the amount of predictors in a dataset increases. Remember how in elementary science we learn that volume grows quicker than area and whatnot, well similarly 3D-volume is has less space to fill than 4D volume, etc. Which means that points which might be really close in 3D become pretty far removed in 4D because there's a whole new axis by which they could be different.

The more dimensions you add the more extreme the effect and it grows quickly. 

It renders techniques like [[1. Cosmos/k-Nearest Neighbor\|k-Nearest Neighbor]] unusable because, in high dimensional spaces, your neighbors might as well be on another planet.

It also makes it so that for higher dimensional datasets, most data points are closer to the boundaries of the dataset than to other points which turns what should be an [[Interpolation\|interpolation]] problem (the easy stuff that we like which means predict within a given scope of data) into an [[Extrapolation\|extrapolation]] problem where we need to extend limited data to fill in the gaps (really relevant in [[Time Series Analysis\|Time Series Analysis]]).

It can be sometimes be sidestepped if we have information about the structure of the data under consideration.
## References
