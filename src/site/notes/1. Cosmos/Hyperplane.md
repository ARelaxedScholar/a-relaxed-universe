---
{"dg-publish":true,"permalink":"/1-cosmos/hyperplane/","created":"2025-01-22T11:17:14.308-05:00","updated":"2024-12-11T22:59:04.633-05:00"}
---

202412112156
Status: #idea
Tags: 
State: #nascient
# Hyperplane

In a $p-$dimensional space, a hyperplane is a flat affine subspace of dimension $p-1$.
By their very definition, they split a $p$ dimensional space into two parts as there's only one axis left. The [[1. Cosmos/Maximal Margin Classifier (Optimal Separating Hyperplaene)\|Maximal Margin Classifier (Optimal Separating Hyperplaene)]] and its extension the [[1. Cosmos/Support Vector Machine (SVM)\|Support Vector Machine (SVM)]] both make use of this fact.

In general, the equation for such a plane is:
$$
\beta_0+\beta_1X_1+\beta_2 X_2+\dots+\beta_pX_p=0
$$

You check that a point lies on the hyperplane by plugging the point in the equation and seeing if the equation is satisfied.

By that logic if we assume that 
$$
\beta_0+\beta_1X_1+\beta_2 X_2+\dots+\beta_pX_p<0
$$
this tells us that $X$ lies below the hyperplane, on the other hand if we get:
$$
\beta_0+\beta_1X_1+\beta_2 X_2+\dots+\beta_pX_p>0
$$
the point lies atop it.

It is typically a good idea to check where the $0$ vector lies to have a better idea of the space.

## References
