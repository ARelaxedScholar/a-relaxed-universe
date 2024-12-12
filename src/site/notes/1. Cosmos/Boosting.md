---
{"dg-publish":true,"permalink":"/1-cosmos/boosting/","created":"2024-12-11T21:03:13.688-05:00","updated":"2024-12-11T21:36:47.760-05:00"}
---

202412112103
Status: #idea
Tags: [[1. Cosmos/Decision Trees\|Decision Trees]]
State: #nascient
# Boosting

Anothe method that is often used with [[1. Cosmos/Decision Trees\|Decision Trees]] to make them suck less.

in comparison to [[1. Cosmos/Bagging (Boostrapped Aggregation)\|Bagging (Boostrapped Aggregation)]] and [[1. Cosmos/Random Forests\|Random Forests]] that generate bootstrapped sample and fit models to data.

- Boosting adopts are more refined approach. It fits a small model (small because of constraints put on it.) and computes some loss metric
- Then it fits another model that predicts the loss essentially compensating for the loss of the first model
- Then another model is fit to the aggregated loss 
- Etc.

This approach is done slowly through three tuning parameters $d$ which controls the number of splits (leads to $d+1$ terminal nodes), $\lambda$ which adds a shrunken version of the new tree to the full model, and $B$ which controls the amount of trees we fit.

Contrarily to [[1. Cosmos/Random Forests\|Random Forests]] and [[1. Cosmos/Bagging (Boostrapped Aggregation)\|Bagging (Boostrapped Aggregation)]] trees, we will absolutely overfit to the training set if we set $B$ too high, this overfitting thanks to the $\lambda$ parameter if it happens will happen extremely slowly.

$\lambda$ is typically a small value like $0.01$ or $0.001$. Obviously the right choice will vary based on the problem. Too compensate the small size (as recall, this represents the "fraction" of the prediction of tree $t_k$ that we add for our prediction $\hat f(x)$)

$d$ as mentioned represents the numbre of splits, considering the approach used here, there is often no need for too much complexity at the tree level since whatever error is made will be corrected by other trees down the line, for those reasons $d=1$ is often a good choice. 
In which case we have a special case of trees, called stumps. In general, $d$ represents something called the $interaction$ $depth$ which is a fancy way of saying the number of variables we allow to interact within any given tree. We can pick it through [[Cross Validation\|Cross Validation]] similarly to $\lambda$.

Still this type of model is really powerful and often achieves higher accuracy than random forests (which itself typically beats bagging trees through decorrelation.)

### Advantages
- Slow learning often leads to better fit which is the approach promoted by this model
- Typically dominates random forests on equal grounds
- Slightly more interpretable since for $d=1$ we have an additive model.
- Thanks to the built-in correlation between trees, each tree need not be as big.
### Cons
- Can overfit if $B$ is too big.


## References
