---
{"dg-publish":true,"permalink":"/1-cosmos/decision-trees/","created":"2024-12-11T20:03:40.365-05:00","updated":"2024-12-11T21:36:32.982-05:00"}
---

202412112003
Status: #idea
Tags: 
State: #nascient
# Decision Trees

Alone is often a weak model.
Easy to interpret.
Is obtained through greedy top down recursive splitting.
Regions are high dimensional boxes that DON'T overlap
It is better to fit a large tree and prune it, than to split until we cannot get splits that
decrease the [[Residual Sum of Squares (RSS)\|Residual Sum of Squares (RSS)]] more than some threshold since some weak splits might open the way to great splits later on.


[[Regression Trees\|Regression Trees]]
[[1. Cosmos/Classification Trees\|Classification Trees]]

### Pros
- Easy to explain, the simplest model there is.
- More closely mirror human decision making than other method
- Trees can easily handle qualitative predictors without the need for dummy variables.
### Cons
- Generally fail when it comes to predictive accuracy
- Not robust, small change in data often leads to big change in the tree.
These cons can be paliated using respectively
[[1. Cosmos/Bagging (Boostrapped Aggregation)\|Bagging (Boostrapped Aggregation)]]
[[1. Cosmos/Random Forests\|Random Forests]]
[[1. Cosmos/Boosting\|Boosting]]
and
[[1. Cosmos/Bayesian Additive Regression Trees (BART)\|Bayesian Additive Regression Trees (BART)]]

through someting called [[Ensembling\|Ensembling]].
## References
