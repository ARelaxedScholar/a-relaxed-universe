---
{"dg-publish":true,"permalink":"/1-cosmos/k-nearest-neighbor/","created":"2024-11-25T20:00:25.199-05:00","updated":"2024-11-29T19:45:05.334-05:00"}
---

202411252000
Status: #idea
Tags: [[Machine Learning\|Machine Learning]], [[Non-Parametric Model\|Non-Parametric Model]]
State: #nascient
# k-Nearest Neighbor

Typically a [[Classification\|Classification]] algorithm in the [[Machine Learning\|Machine Learning]] family—which can be used for regression—that assigns a label to a new observation based on the label of its $k-Nearest~~ Neighbors$.

Definition:
$$
\hat Y(x) = \frac{1}{k}\sum_{x_i\in N_k(x)}y_i
$$

In English, consider all the $x_i$ within the neighborhood of $x$.
Look at their label $y_i$, and take the average. Here the assumption is that the label is encoded as $0$ and $1$, and so this feasible. Assuming you have more than two levels, you just assign $x$ to whichever label occurs more often in its neighborhood. You can convince yourself that this is equivalent to the above formula.

k-NN is a form of [[Non-Parametric Model\|Non-Parametric Model]], a type of model that does not make assumptions about the functional form of a model. Here the model will be slightly different for every neighborhood.

The main assumption this model makes is that observations which are close in space are similar. It is an example of a low bias, high variance model! 

In a [[1. Cosmos/Regression\|Regression]] context, we'd call it, [[k-Nearest Neighbor Averaging\|k-Nearest Neighbor Averaging]]. Using the exact same idea, but instead of assigning to the majority label of the $k-Nearest ~~Neighbors$, we'd assign to the **average response level** of these neighbors.

k-Nearest Neighbor is likely the most intuitive machine learning algorithm of them all.

The only complexities are that:
- as opposed to most algorithms $k$ being smaller means more complex. (Intuitively, we have $n/k$ effective parameters in the dataset based on where $x$ falls in the dataset assuming non-overlapping clusters.)
- The "closest" and "neighborhood" are entirely dependent of the measure of distance. Typically it is the [[1. Cosmos/Euclidean distance\|Euclidean distance]] but there's nothing in the specification of the algorithm that forces this move.

Besides that, this is a deceptively simple but effective method that tries to approximate the Bayesian Averaging Estimator ($E(Y|X)$), which is the optimal estimator you could hope for, by averaging a "neighborhood" of "local" points rather than the values of the points exactly at $X$ which in practice happens is not often feasible.

## References
