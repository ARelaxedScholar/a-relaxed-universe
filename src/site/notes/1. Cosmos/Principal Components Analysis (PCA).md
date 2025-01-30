---
{"dg-publish":true,"permalink":"/1-cosmos/principal-components-analysis-pca/","created":"2025-01-22T11:17:14.304-05:00","updated":"2024-12-12T11:10:06.010-05:00"}
---

202412121103
Status: #idea
Tags: [[Unsupervised Learning\|Unsupervised Learning]], [[1. Cosmos/Linear Algebra\|Linear Algebra]], [[1. Cosmos/Singular Value Decomposition\|Singular Value Decomposition]]
State: #nascient
# Principal Components Analysis (PCA)

Data exists in a $p-$dimensional space.
But not all dimensions are made equal.

PCA seeks to find the dimensions across which variability is biggest.
The first component represents the highest variability (and the size of it represents how much variability), and the loading vector represents the direction of maximum variability.

The principal components are sorted in decreasing order such that that the last principal component $p$ is the one where variation is the smallest.

The principal components are orthogonal

### Pros
- Useful for plotting high dimensional data.
- If our task align with those dimensions of high variability, a really nice technique
- Based on strong linear algebra foundations.
- Can be used for imputation as well

### Cons
- Not really interpretable



## References
