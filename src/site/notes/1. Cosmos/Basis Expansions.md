---
{"dg-publish":true,"permalink":"/1-cosmos/basis-expansions/","created":"2025-01-22T11:17:14.278-05:00","updated":"2024-12-11T17:07:26.146-05:00"}
---

202412101913
Status: #idea
Tags: 
State: #nascient
# Basis Expansions

Often the assumption is linearity is done either because it's convenient and accurate enough (fitting as any polynomial will have a linear component as part of its [[Taylor Series Expansions\|Taylor Series Expansions]]) or because there's no other way around it [[1. Cosmos/Curse of Dimensionality\|Curse of Dimensionality]] and [[Overfitting\|Overfitting]].

But what do we do if we want something more complex than [[1. Cosmos/Linear Regression\|Linear Regression]], [[1. Cosmos/Logistic Regression\|Logistic Regression]] and [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]] (or its sibiling [[1. Cosmos/Quadratic Discriminant Analysis (QDA)\|Quadratic Discriminant Analysis (QDA)]].)

Well, in such a case a suitable approach is the basis expansion. The idea is simple, but the consequences are anything but. It is actually similar to one of the ways to obtain the [[1. Cosmos/Quadratic Discriminant Analysis (QDA)\|Quadratic Discriminant Analysis (QDA)]].

What do you do? It's very simple.

Apply some transformation $h_m(X): \mathbb{R}^p \mapsto \mathbb{R}$  where $h_m$ is the $m$th such transformation of $X$.
We can then model $f(x)$ as:
$$
f(x)=\sum_{m=1}^M\beta_mh_m(X)
$$
In other words, we apply transformations to the data which in effect warps the space and then try to fit lines to that space as we would do typically.

Similarly to how a straight line on a plane is curvy once you bring it back to the planar world, the lines fit in these warped spaces actually end up being quite complex which is exactly what we seek here.

This gives us complexity in how we can fit the data, but we only have so much data to fit, as a result even in the basis expansions method which specific basis to fit is not clear.

By default this is univariate, that is we expect one predictor.

If we want to fit multiple predictors to an output variable, while keeping the power of basis expansion, if we think the relationship between predictors is strictly additive using [[1. Cosmos/Generative Additive Models (GAM)\|Generative Additive Models (GAM)]]

Note that in practice many statistical packages allow you to do interaction between two features modeled with basis expansion, but if you want to put it in a [[1. Cosmos/Generative Additive Models (GAM)\|Generative Additive Models (GAM)]], you need to ensure to deal with that interaction locally first so that when added to the model, the additivity assumption is maintained.

## Common Types
[[1. Cosmos/Splines (Piecewise Polynomials)\|Splines (Piecewise Polynomials)]]
## References
