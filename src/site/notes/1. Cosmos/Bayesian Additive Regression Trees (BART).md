---
{"dg-publish":true,"permalink":"/1-cosmos/bayesian-additive-regression-trees-bart/","created":"2025-01-22T11:17:14.294-05:00","updated":"2024-12-11T21:52:05.878-05:00"}
---

202412112122
Status: #idea
Tags: [[1. Cosmos/Decision Trees\|Decision Trees]], [[Bayes Theorem\|Bayes Theorem]], [[Markov Chain Monte Carlo\|Markov Chain Monte Carlo]]
State: #nascient
# Bayesian Additive Regression Trees (BART)

Similar to both [[1. Cosmos/Random Forests\|Random Forests]] and [[1. Cosmos/Boosting\|Boosting]]. 
Each tree is constructed randomly as in random forest, and is built sequentially through an approach where each successive tree tries to capture information about the previous trees like in [[1. Cosmos/Boosting\|Boosting]]

Main novelty: The how trees are generated

We fit $K$ trees.
1. For each tree we start with a root node who's decision is just the mean and compute the residuals of that tree.
2. We compute the residual
3. We apply some perturbation to the tree randomly at each step (either change tree structure by adding/removing a branch, or changing the prediction in the terminal nodes)
4. We consider the residual obtained when considering the output of all the trees until now.
5. Repeat for $B$ iterations
6. Enjoy!?

That's really it, the result is then obtained by taking the average of the predictions of each tree beyond a burn-in phase $L<B$ , and across all trees $K$.

### Pros
- Boasts exceptional OOB error with minimal tuning (Good default values are $L=100, K=200, B=1000$)
- Harder to overfitting using it
- Strong theoretical backing since we are using [[Bayes Theorem\|Bayes Theorem]] and are drawing a new tree from the posterior distribution, the algorithm can also be seen as a [[Markov Chain Monte Carlo\|Markov Chain Monte Carlo]].



## References
