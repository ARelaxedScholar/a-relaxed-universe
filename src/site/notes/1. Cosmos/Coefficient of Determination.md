---
{"dg-publish":true,"permalink":"/1-cosmos/coefficient-of-determination/","created":"2025-01-22T11:17:14.055-05:00","updated":"2024-05-20T00:56:34.060-04:00"}
---


202405181414
Status: #idea
Tags: [[Regression Analysis\|Regression Analysis]] 
# Coefficient of Determination
Often denoted $R^2$ It is a measure that tells us the proportion of the variance around the mean that is explained by our model. In the [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]] case, this measure and the correlation are the same.

It is computed as follows:
$$
R^2 = \frac{SS_{reg}}{SS_{total}} = 1-\frac{SS_{reg}}{SS_{total}}
$$

But be careful, [[Correlation\|Correlation]] and [[1. Cosmos/Coefficient of Determination\|Coefficient of Determination]] are not the same in general. In fact, as soon as we get to the multivariate case they are no longer equal since [[Correlation\|correlation]] measures the linear relation between two variables, and the coefficient of determination measures the explanatory power of an entire model.

Similarly to the [[Correlation\|Correlation]] it is bounded between 0 and 1, where 1 indicates a perfect explanatory power and 0 explains basically no power (no better than the mean line itself.)

There is a concept called [[Adjusted Coefficient of Determination\|Adjusted Coefficient of Determination]] which directly follows from it, and that is important because in a parametric model adding more parameters will NEVER make my model's fit worse. It might leave it the same, but even assuming the new parameter has no value I can always set it to 0 and revert to a less parameterized model. For that reason, we need to dock points from the score of models with more parameters to account for the fact that more parameters can significantly improve a model out of sheer luck.

## Warning about Overreliance
$R^2$ is cool, but it is far from perfect. For example, it is not smart enough to realize that a model might fit data out of sheer luck.

You could get a really high $R^2$ on a dataset that is clearly not linear. $R^2$ should only be used if the other assumptions have been confirmed and it is judicious to do so.
## References
[[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]]
