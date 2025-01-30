---
{"dg-publish":true,"permalink":"/1-cosmos/spectral-clustering/","created":"2025-01-22T11:17:14.105-05:00","updated":"2024-12-12T14:00:17.979-05:00"}
---

202412121304
Status: #idea
Tags: 
State: #nascient
# Spectral Clustering

A graph based method which turns the clustergin problem into one o disconnecting graphs with the minimal cost.   

1. Form a similarity graph containing all the observations using some similarity measure like the [[Gaussian Kernel\|Gaussian Kernel]] or $k-nearest$ neighbors to compute edges.
2. Then from the graph you can create a new graph where observations that are too dissimilar do not have an edge, and those that are similar do (note that we don't care about observations similarity to themselves). We prune the graph and only retain significant connections.
3. We compute the Laplacian matrix $L$ of the graph which has connection [[Laplace's Equations\|Laplace's Equations]] and which is given either by $A^tA$ where $A$ is the incidence matrix of our graph, or alternatively by $D-B$ where $D$ is the degree matrix with the degree of each node along the diagonal, and $B$ is an adjacency matrix. Note that this is the *unnormalized version* there exist two others:
	- **Normalized** (symmetric): $L_{\text{sym}} = D^{-1/2}LD^{-1/2}$.
	- **Normalized (random walk)**: $L_{\text{rw}} = I - D^{-1}A$.
	- Sadly which we pick will affect the results.
1. Thanks to the properties of the matrix, we know for sure that $0$ will be an eigenvalue of the matrix, the matrix is positive semi-definite, and yeah.
2. To split in two groups we start from the smallest eigenvalues and consider the smallest eigenvalue (excluding) the $0$ and use it's eigenvector (the [[Fiedler Vector\|Fiedler Vector]]) to partition in two sets.

If we want to do more than two clusters, we start the same way but then:
1. we select the $K$ first eigenvectors starting from the smallest (still excluding the zero eigenvector.)
2. From these eigenvector we form a matrix $n\times k$ where each column is an eigenvector, this is called the [[Spectral Embedding\|Spectral Embedding]]
3. We run a standard clustering algorithm on this matrix and cluster in the spectral space typically using $k-means$.
4. We assign the observations to the cluster obtained from the previous step.

Once we went through the previous processing step, the hope is that the clusters become linearly separable in the spectral embedding space (which generally is true.) As a result, $k-means$ is a great tool to use in conjunction with spectral clustering.

## References
