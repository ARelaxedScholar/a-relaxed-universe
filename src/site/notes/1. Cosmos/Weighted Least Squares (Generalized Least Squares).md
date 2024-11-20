---
{"dg-publish":true,"permalink":"/1-cosmos/weighted-least-squares-generalized-least-squares/","created":"2024-08-31T23:47:13.920-04:00","updated":"2024-06-20T16:01:40.959-04:00"}
---

202406201556
Status: #idea
Tags:  [[Regression Analysis\|Regression Analysis]]
State: #nascient
# Weighted Least Squares (Generalized Least Squares)
We use WLS when the assumption of homoscedasticity is broken. If it's not, we will use [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]] or [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]].

If not, we need to account for the fact that the residuals are not the same by multiplying each residual (the thing we use to find the parameters) by some weight, and that weight is:
$$
w_i = \frac{1}{\sigma^2_i}
$$
Such that the weighted sum of errors become:
$$
\sum_{i=1}^nw_i(y_i-\hat y_i)
$$

## References
