---
{"dg-publish":true,"permalink":"/1-cosmos/feature-selection/","created":"2024-12-09T08:54:05.412-05:00","updated":"2024-12-09T08:59:19.591-05:00"}
---

202412090854
Status: #idea
Tags: [[Machine Learning\|Machine Learning]], [[1. Cosmos/Curse of Dimensionality\|Curse of Dimensionality]], [[1. Cosmos/Regularization\|Regularization]]
State: #nascient
# Feature Selection

The bread and butter of data engineers from what I heard. One of the most important parts and difficult as well.

How do I select from a bunch of potentially important data the best features for whatever target I have. This is feature prediction and this is in general not easy.
It is crucial because of the [[1. Cosmos/Curse of Dimensionality\|curse of dimensionality]] and the fact that for most models we can not simply take all the features we have in a model, chuck them in a model and call it a day.

Even assuming we could, there are many contexts where our goal is [[1. Cosmos/Inference\|inference]] rather than strict [[Prediction\|prediction]] in which case, we will want reasonable predictive power yes, since this is what will serve as a validator that whatever we observe is real, but more importantly we will want interpretability.

Something that an hypothetical model with 200 features would lack.


[[Subset Selection\|Subset Selection]]
[[1. Cosmos/Ridge Regression\|Ridge Regression]]
[[Lasso Regression\|Lasso Regression]]
## References
