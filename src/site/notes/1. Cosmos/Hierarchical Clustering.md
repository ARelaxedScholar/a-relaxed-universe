---
{"dg-publish":true,"permalink":"/1-cosmos/hierarchical-clustering/","created":"2024-12-12T12:03:14.118-05:00","updated":"2024-12-12T12:35:43.064-05:00"}
---

202412121203
Status: #idea
Tags: 
State: #nascient
# Hierarchical Clustering

As opposed to [[1. Cosmos/K-Means Clustering\|K-Means Clustering]] which requires to specify the number of clusters we expect, hierarchical clustering starts with singular data and then agglomerates it as it progresses up it's an example of an [[Agglomerative Clustering Method\|Agglomerative Clustering Method]] using AGNES.

A top-down divisive approach DIANA exists and give similar results, but it is slower.

Thanks to how it works, we get a measure of "similarity" of two elements given by the level at which they first became connected. Observations that are connected near the top might be quite different as observations that are connected in the first steps should be quite similar.

Thanks to this process, get a global vision of all possible clusters as the nodes we have at each step.

The process gives rise to a tree structure named a [[Dendrogram\|Dendrogram]].

This algo makes an assumption of the hierarchality of splits will lead to the best splits, in the sense that splits are nested. If I am going one way  th eproperties are progressively  getting more specific, and other branches would be different.

But if I have things like gender and nationality, splitting based on gender and then nationality might give the best clusters, but then I have say Japanese people on both sides which fails the assumption of hierarchy.

The Algo:
1. Start from $n$ clusters, every observation is its own cluster
2. Combine to one cluster the pair observations that are closest to each other so that we have $(n-1)$ clusters
3. Of cluster pairwise comparison until every observation belongs to one cluster

To do that we need a measure of dissimilarity which by and large is the [[1. Cosmos/Euclidean distance\|Euclidean distance]]
and we need a way to measure similarity between clusters which contains multiple elements, that is where [[1. Cosmos/Linkage\|Linkage]] comes into play, the four most common are *complete*, *average*, *single*, and *centroid*.

Average and complete are generally preferred as opposed to single, centroid is used in genomics but can lead to inversion which is when two clusters are merged below the level where they meet? Idk.

No matter the case the method is highly reliant on the dissimilarity measure used so it is important to know why we picked it.

A table with them can be found there: [[1. Cosmos/Linkage\|Linkage]]
![Pasted image 20241212120658.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020241212120658.png)
![Pasted image 20241212121213.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020241212121213.png)![Pasted image 20241212123113.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020241212123113.png)
## References

