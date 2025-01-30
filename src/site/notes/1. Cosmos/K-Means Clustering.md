---
{"dg-publish":true,"permalink":"/1-cosmos/k-means-clustering/","created":"2025-01-22T11:17:14.055-05:00","updated":"2024-12-12T12:03:03.962-05:00"}
---

202412121200
Status: #idea
Tags: 
State: #nascient
# K-Means Clustering

We specify a $K$.
The goal is to minimize the intra-cluster variance.
In practice finding a global optima is $NP-$hard.

But there is an approximate solution that can give a local optima.
1. Give labels randomly
2. Compute the centroid for each each class
3. Assign each observation to the class of whose the centroid is closest
4. Repeat until classes stop changing

Since this is a local optimum, we need to run it multiple times and select from those we selected the one that minimizes the error.

## References
