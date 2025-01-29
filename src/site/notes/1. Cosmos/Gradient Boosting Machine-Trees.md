---
{"dg-publish":true,"permalink":"/1-cosmos/gradient-boosting-machine-trees/","created":"2025-01-22T11:17:14.321-05:00","updated":"2024-07-20T03:32:56.705-04:00"}
---

 202407200332
Status: #idea
Tags: [[Deep Learning\|Deep Learning]]
State: #nascient
# Gradient Boosting Machine-Trees
Related to [[1. Cosmos/Random Forests\|Random Forests]].

2 metas in AI:
Bagging : take multiple models into an ensemble and take the mean of the inferences. (What a Random Forest does)
Boosting : make an inference using a simple tree. Then find a tree that makes an inference for the error of the first tree. And then find one that finds the inference for this tree. Etc. Instead of taking the mean of the inferences you take the sum. Gradient Boosting trees or machines in a nutshell.

Advantages:
- More accurate (not necessarily by much)

Cons:
- Contrarily to Random Forest, you can overfit them.

Best seen as a possible next step for when random Forests are not good enough.


## References



#machinelearning