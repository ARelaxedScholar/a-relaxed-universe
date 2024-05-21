---
{"dg-publish":true,"permalink":"/1-cosmos/properties-of-least-square-estimators-in-slr/"}
---

202405161153
Status: #idea
Tags: [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]]
# Properties of Least Square Estimators in SLR

$$\hat\beta_1 = \frac{SSxy}{SSxx}$$ where $SS_{xy} = \sum_{i=1}^n X_iY_i - n\bar X\bar Y = \sum_{i=1}^n Y_i(X_i - \bar X)=\sum_{i=1}^n X_i(Y_i - \bar Y)=\sum_{i=1}^n (X_i - \bar X)(Y_i - \bar Y)$
and $SS_{xx} = \sum_{i=1}^n X_i^2 - n\bar X^2 =\sum_{i=1}^n (X_i - \bar X)^2$

$$
\hat\beta_0 = \bar Y-\hat\beta_1 \bar X
$$
ergo the fitted line (estimate) is:
$$
\hat Y = \hat \beta_0 + \hat \beta_1 X_i
$$
## References
