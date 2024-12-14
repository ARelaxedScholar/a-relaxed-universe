---
{"dg-publish":true,"permalink":"/1-cosmos/support-vector-machine-svm/","created":"2024-12-11T21:52:49.459-05:00","updated":"2024-12-11T23:50:09.704-05:00"}
---

202412112152
Status: #idea
Tags: 
State: #nascient
# Support Vector Machine (SVM)

Considered one of the best out of the box classifiers.

Generalization of the simple and intuitive [[1. Cosmos/Maximal Margin Classifier (Optimal Separating Hyperplaene)\|Maximal Margin Classifier (Optimal Separating Hyperplaene)]] which while elegant requires [[Linearly Separable\|Linearly Separable]] data, as a result it is not applicable to most data sets.

Still if we relax the assumption of linear separability we get a very potent model.

It is a great model that can be used both for linear decision problems, but also for non-linear ones through extension of its feature space, or the [[Kernel Trick\|Kernel Trick]].

## How do we deal with Non-Linear Data

### The Simple Approach
The simplest option is to do what we've been doing all along, enrich the feature space with transformations of the original predictors and fit a model to that new space, a boundary that is linear in this space will be quite non-linear when we consider only the original variables.

But this is anticlimatic, and for good reasons. The support vector machine is known because of its use of kernels. It enriches the feature space, yes, but in a really specific way, a way that avoids us having to deal with all those computations due to enlarging the feature space which at times can become intractable.
### The Kernel Trick
Essentially, the support vector machine makes use of the fact that for the computation of the point that maximizes the $M$, rather than using the actual observations themselves, we relate them through the inner product.

Well, anyone familiar with linear algebra knows that every innner product is associated with some [[Symmetric Positive Definite Matrix\|Symmetric Positive Definite Matrix]] and vice-versa every [[Symmetric Positive Definite Matrix\|Symmetric Positive Definite Matrix]] defines some inner product (where the standard one is just the identity matrix), as a result we have a literal infinity of kernels to choose from.

The kernel trick makes use of that realization to pick kernels that best use properties of the data, that is kernels that would be most meaningful for the specific topology of our dataset and fit an hyperplane that is linear with respect to that space without having to actually convert the dataset to it.

Classical ones are listed below:
- [[Polynomial Kernel\|Polynomial Kernel]]
- [[Radial Kernel\|Radial Kernel]] (infinite dimension and therefore could never be extended to using the simple approach)
- [[Gaussian Kernel\|Gaussian Kernel]]

Note that technically other methods such as the logistic regression model could put those kernels to use, but for historical reasons, the use of kernels is much more widespread when talking about [[1. Cosmos/Support Vector Machine (SVM)\|Support Vector Machine (SVM)]] and the two are almost synonymous (well not quite synonymous, but one brings to mind the other.)

## So what do we do when there are more than two classes?
There are two main ways:
### One-Versus-One
1. Create a model for each possible pair of levels.
2. Assign to a new observation the label that was voted by the most models in that context

### One-Versus-All
1. Fit $K$ models, each one comparing class $i$, to the rest.
2. Assign to a new observation the label for which the distance to the hyperplane ($\beta^TX$) is maximized, as if we recall from [[1. Cosmos/Maximal Margin Classifier (Optimal Separating Hyperplaene)\|Maximal Margin Classifier (Optimal Separating Hyperplaene)]], this distance represents our confidence.

Obviously, since we want everything to be comparable, we need to fit the models using the same fitting procedure, that is same $C$, same kernel, etc.

## A Puzzling Relationship to the [[1. Cosmos/Logistic Regression\|Logistic Regression]] Model.
Hinge loss function. 
[[1. Cosmos/Logistic Regression\|Logistic Regression]] and [[1. Cosmos/Support Vector Machine (SVM)\|Support Vector Machine (SVM)]] often give very similar results.

- When the data is well separated, SVM performs better, otherwise Logistic Regressions is generally preferred.
- For probability estimation, [[1. Cosmos/Logistic Regression\|Logistic Regression]] is the pick. (Classification of illnesses)
- For non-linear decision boundaries, the [[Kernel Trick\|Kernel Trick]] puts [[1. Cosmos/Support Vector Machine (SVM)\|Support Vector Machine (SVM)]] ahead.
## References
