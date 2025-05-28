---
{"dg-publish":true,"permalink":"/1-cosmos/classification-trees/","created":"2025-01-22T11:17:14.055-05:00","updated":"2025-05-28T18:09:07.989-04:00"}
---

202412112028
Status: #idea
Tags: [[1. Cosmos/Machine Learning\|Machine Learning]], [[1. Cosmos/Classification\|Classification]]
State: #awakened 
# Classification Trees

Typically split using [[Gini Index\|Gini Index]] or [[Entropy (Deviance)\|Entropy (Deviance)]] since they are more sensitive (and therefore useful for growing a tree) than classification error which is not sensitive enough.

The classification is made based on the mode at each level. They are one of the most easily interpretable type of [[1. Cosmos/Machine Learning\|Machine Learning]] models used for [[1. Cosmos/Classification\|classification]].

As a general rule though, they have the opposite problem to [[1. Cosmos/Logistic Regression\|Logistic Regression]], that is a very low bias (they can fit pretty much anything), but a really high variance (they can fit pretty much anything.) This is problematic because to make the model any good on training data, you often need the tree to be rather deep, but once a certain depth is reached it will suck on your testing set. Not only that, tweaking a single observation might significantly affect the fit of your models which makes them comedically brittle.

This is why, you will generally either want to make use of [[1. Cosmos/Regularization\|Regularization]] (which with classification trees mean pruning,) keep the depth relatively low (a single stub can often give you enough predictive power) or just use a better model that ensembles a bunch of them (wisdom of the masses type-beat.)

I currently got notes on:
[[1. Cosmos/Random Forests\|Random Forests]]
[[1. Cosmos/Gradient Boosting Machine-Trees\|Gradient Boosting Machine-Trees]]

Which are two of the latter type, and arguably the most important to know in practical machine learning.
## References
