---
{"dg-publish":true,"permalink":"/1-cosmos/loss/","created":"2024-08-31T23:47:14.145-04:00","updated":"2024-12-13T08:00:00.204-05:00"}
---

202405031413
Status: #idea
Tags: [[Statistics\|Statistics]]
# Loss (Residual)

It is nothing more and nothing less than the difference between the predicted value and the actual value of a given observation.

So:
$$
\epsilon = y_{pred}-y_{ground ~truth}
$$

The loss function, is typically going to be a function that accumulates those residuals and then try to reduce that accumulation. That accumulation can be done using [[Mean Absolute Error (L1 Loss)\|Mean Absolute Error (L1 Loss)]] or [[Mean Squared Error (L2 Loss)\|Mean Squared Error (L2 Loss)]] or other relevant [[Loss Functions\|Loss Functions]]. The latter is much more often used thanks to the nice properties it has. In fact it will yield the best line under the [[1. Cosmos/Assumptions of Simple Linear Regression\|Assumptions of Simple Linear Regression]]. On the other hand, we use the former when we know that our model must be resistant to outliers.



## References
