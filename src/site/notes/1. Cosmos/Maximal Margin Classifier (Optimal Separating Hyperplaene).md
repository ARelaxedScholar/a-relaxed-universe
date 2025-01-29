---
{"dg-publish":true,"permalink":"/1-cosmos/maximal-margin-classifier-optimal-separating-hyperplaene/","created":"2025-01-22T11:17:14.234-05:00","updated":"2024-12-11T22:59:04.641-05:00"}
---

202412112207
Status: #idea
Tags: [[1. Cosmos/Classification\|Classification]], [[1. Cosmos/Hyperplane\|Hyperplane]], [[1. Cosmos/Linear Methods for Classification\|Linear Methods for Classification]]
State: #nascient
# Maximal Margin Classifier

When a data set is said to be [[Linearly Separable\|Linearly Separable]], then there exists some hyperplane that cuts through the data in such a way that all the observations of one type lie on one side, and all those of the other lie on the other side.

In such a case, that line becomes model for classification. The issue is that if data is linearly separable, there's an infinity of such lines, so to restrict our problem to one that can be approximated and solved by optimization, we focus on the one that maximizes the margin.

We define the margin as the distance from the classifier to the closest observation (the smallest distance.)

This classifier by its definition becomes the "optimal" classifier in the sense that it maximizes the distance between observation of differing types.

The notion of [[Support Vectors\|Support Vectors]] come here, as within the dataset only those closest observations to the decision hyperplane truly affect the fit, change these points and the hyperplane will have to shift, but touch any other point and we don't really care.

Hence this model is resistant to outliers (as long as the assumption holds.)
![Pasted image 20241211222349.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020241211222349.png)
for $y_i \in \{-1, 1\}$

This elegant optimization formula condenses in one formula the idea that where the point lies $\beta...$ and the assigned label $y_i$ need to match, after all we only get negative signs here if there's a disagreement between the sign when putting the parameter vector $\beta$ in the equation of the hyperplane.

On the other hand, it can be shown that the distance from the plane is exactly $\beta^TX$ , as a point on the line will have yield $0$.

Since our goal is to maximize $9.11$, finding the set of $\beta$ which maximizes this is exactly what we want. Note that if the assumption breaks, there will be no solution such that the LHS is greater than $M$ or even $0$ for that matter.

We need to generalize the idea and consider [[1. Cosmos/Support Vector Classifiers (Soft Margin Classifier)\|Support Vector Classifiers (Soft Margin Classifier)]] and their generalization [[1. Cosmos/Support Vector Machine (SVM)\|Support Vector Machine (SVM)]]
$$

$$

## References
