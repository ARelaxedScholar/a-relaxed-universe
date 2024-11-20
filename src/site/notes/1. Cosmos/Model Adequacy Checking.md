---
{"dg-publish":true,"permalink":"/1-cosmos/model-adequacy-checking/","created":"2024-08-31T23:47:13.833-04:00","updated":"2024-06-07T14:06:29.636-04:00"}
---

202405171706
Status: #idea
Tags: [[Regression Analysis\|Regression Analysis]]
# Model Adequacy Checking
In statistics we always deal with models. 

And each model has a set of assumptions tied to its usage. Model Adequacy Checking is the science of ensuring that a given dataset fulfills all the assumptions that are required to use the model in question.

For the assumptions of [[Linear Regression Model\|Linear Regression Models]] we do the following assumptions:

- Linearity (There's a linear (in $X$) relation between the predictor variables and the response variables)
- Normality (The error terms are normally distributed)
- Homoscedasticity (The error terms are distributed according to the same variance (error does not vary as $X$ varies))
- Independence of errors ($\varepsilon \sim N(0, \sigma^2)$)

As a general rule, besides for linearity we are focused on the error terms. The issue is that typically the error terms can be all over the place, despite the assumptions holding. After all, while they all have mean $0$ (by assumption), no specific bounds on there variance exists. Therefore we need to scale them so that they're in the same ballpark. 

After all, in a context with a really high variance errors being far apart, will mean less than similar spreads in a low variance context. Therefore to uniformize the errors and make it so we can analyze the residuals, similar to how we normalize the gradients in calculus 3 to get only the directions, here we will "standardize" or "studentize" the errors to put them all on the same scale.

## Uniformizing the $\varepsilon$ terms:
**Standardized Residuals**
For standardized residuals, we divide each error term by its own standard deviation.
$$
\varepsilon_i^* = \frac{\varepsilon_i}{\sqrt{Var(\varepsilon_i)}}=\frac{\varepsilon_i}{\sqrt{MSE(1-h_{ii})}}
$$


**Semi Standardized Residuals** ~ To Check non-constant variance
$$
\varepsilon_i^* =\frac{\varepsilon_i}{\sqrt{1-h_{ii}}}
$$
We will use this by plotting it against $\hat y$ and observing the variation around the regression line.
**Studentized Residuals**:
$$
$$

**Semi Standardized Residuals**
## Checking for Constant Variance
You can also use a *scale-location* plot, which plots the square root of the absolute value of $\varepsilon^*$ against $\hat y$.
[[Semi-Standardize vs Y Hat\|Semi-Standardize vs Y Hat]]
[[Scale-Location Plot\|Scale-Location Plot]]

## Checking for Normality
[[QQ-Plot\|QQ-Plot]]
[[Boxplot of the Errors (around median 0)\|Boxplot of the Errors (around median 0)]]
[[Histogram\|Histogram]]





## $R^2$ and Adjusted $R^2$
The coefficient of determination called $R^2$ is given by the ratio:
$$
R^2 = \frac{SS_{reg}}{SS_{total}} = 1-\frac{SS_e}{SS_{total}}
$$
It is a crucial number that gives us the proportion of variation that is explained by the regression line.

Why do we need an adjusted version though? Simply because if I wanted to, I could artificially increase $R^2$ by randomly adding new parameters. Indeed, since the new model would have all the old parameters as well, it will never be less performant than the model with less parameters, which is problematic considering I could add parameters thathave some predictive power out of sheer luck.

Therefore to make sure, I only add parameters if they give a substantial advantage, I will "dock" points from my $R^2$ the more parameters there are, to compensate for the random increase in performance a random parameter could give us.

Therefore if the adjusted $R^2$ is still high, I will be able to conclude that indeed thse additions were good.
It is calculated as follows:
$$
R^2_{adj} = 1-((1-R^2)[\frac{n-1}{n-2}])
$$
In practice, we will always use that over $R^2$, especially if we want to compare models with different number of variables.

While $R^2$ is good, one must keep in mind that is by no means perfect. It is possible to get a $R^2$ that is quite high despite not having a linear relation between the predictors and the response variable. Whether that's acceptable should be considered, but while a high $R^2$ typically correlate with linearity, it by no means guarantee it.
## References
