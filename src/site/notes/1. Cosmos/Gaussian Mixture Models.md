---
{"dg-publish":true,"permalink":"/1-cosmos/gaussian-mixture-models/","created":"2025-01-22T11:17:14.228-05:00","updated":"2024-12-12T15:03:39.465-05:00"}
---

202412121424
Status: #idea
Tags: 
State: #nascient
# Gaussian Mixture Models

We try to find:
1. The number of gaussians
2. Their location (mean)
3. Their width (covariance)

We assign a label based on the generator which maximizes the posterior probability.
We might have overlapping labels where points belong to different clusters to varying degrees, so this is a soft clustering method as opposed to something like [[1. Cosmos/K-Means Clustering\|K-Means Clustering]] or [[1. Cosmos/Spectral Clustering\|Spectral Clustering]] where there is no overlap.

It uses the [[Expectation-Maximization Algorithm\|Expectation-Maximization Algorithm]] to find the parameters.

Can cope of different sizes much better than [[1. Cosmos/K-Means Clustering\|K-Means Clustering]]
## References
