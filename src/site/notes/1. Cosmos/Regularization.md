---
{"dg-publish":true,"permalink":"/1-cosmos/regularization/","created":"2025-01-22T11:17:14.214-05:00","updated":"2025-05-28T11:06:13.509-04:00"}
---

202412090844
Status: #idea
Tags: [[Artifical Intelligence\|Artifical Intelligence]], [[1. Cosmos/Machine Learning\|Machine Learning]]
State: #awakening
# Regularization

This is a tax on complexity that is used on models to prevent them from [[Overfitting\|overfitting]] to training data.

Based on the structure of the data the name and way they are applied will be different the logic is pretty much always the same.

1. Take some loss function that we are trying to optimize
2. Add to it the coefficients of the model times some constant $\lambda$ which controls the strength
3. Enjoy!?

This will make it so that optimizing the loss function necessarily involves reducing the coefficients somewhat. A lambda that is near zero or zero will make the function act as essentially unrestrained and will likely be of minimal importance, on the other hand  a $\lambda$ close to infinity will put strong pressure on the model and is likely not what we want (often force the coefficients to linearity.)

They are often used as a [[1. Cosmos/Feature Selection\|Feature Selection]] method and would fall in the category of [[Embedded Feature Selection\|Embedded Feature Selection]], since the feature selection is embedded in the fitting process.

They often lack direct formulas and must be solved numerically.

## Types of Regression per Model Type

### Linear Model
[[1. Cosmos/Ridge Regression\|Ridge Regression]]
[[Lasso Regression\|Lasso Regression]]


## References
