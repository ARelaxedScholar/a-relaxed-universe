---
{"dg-publish":true,"permalink":"/1-cosmos/validation-set/","created":"2025-01-22T11:17:14.331-05:00","updated":"2024-05-20T21:44:36.056-04:00"}
---

202405021003
Status: #idea
Tags: [[1. Cosmos/Machine Learning\|Machine Learning]]
# Validation Set
This is one of the most important components of [[1. Cosmos/Machine Learning\|Machine Learning]] if not the most important thing. As you need to be able to say how good your model is at fitting the data you were given. 

It is the thing that will allow you to identify where roughly you are in the [[Bias-Variance Tradeoff\|Bias-Variance Tradeoff]] spectrum, are you [[Underfit\|underfitting]] and introducing too much [[Bias\|bias]] into the model (Bias can mean different things in different contexts, but in general it is related to the error caused by your model's rigidity) this will typically be due to not running enough [[Epochs\|epochs]] to train your model. You may be  [[Overfitting\|overfitting]] on the other hand which will generally be the result of running too many epochs, or modifying the [[Hyperparameters\|hyperparameters]] too much.

Indeed a validation set is a part of the data that the model does not see during training, the issue is that while the model does not see it during training, you do see your validation set (or at least you can); and you will almost certainly adjust parameters to allow the model to perform better. 

As a result, if you are not careful it is easy to overfit to the validation set simply because you kept tweaking the hyperparameters like the [[Learning Rate\|learning rate]] or whatever.
## References
[[Test Set\|Test Set]]
[[Training Set\|Training Set]]
[[2. White Holes/References/Practical Deep Learning for Coders\|Practical Deep Learning for Coders]]