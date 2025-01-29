---
{"dg-publish":true,"permalink":"/1-cosmos/dbscan/","created":"2025-01-22T11:17:14.164-05:00","updated":"2024-12-12T13:01:15.347-05:00"}
---

202412121249
Status: #idea
Tags: 
State: #nascient
# DBSCAN

Density based approach that relies on density to cluster, it looks for groups within the data with a bunch of observation.

It defines three categories of points:
- Outlier (which are unreachable)
- Reachable (which are near other points but don't have enough points in their neighborhood)
- Core (those with at least $min$ $points$ in their neighborhood, they drive the algo.)

For it you need to define the minimumnumber of point that a point needs to be a core point, once that is done, you just apply the following algo:
1. Pick a random point not in any cluster
2. If point is not core, assign it to the noise cluster
3. Else, build its network of density connected paths (extend a graph from this core point)
4. Assign all the observations in this graph to a new cluster
5. Repeat until every observation has been assigned somewhere.

The noise cluster represents outliers, so if you have a dataset where density is a big component, you can reasonably use DBSCAN for novelty detection.

It could happen that two clusters share non-core points in their graphs, in those cases these points will be assigned randomly. Hence while we only expand the graph if a point has at least $min$ $points$ direct neighbors, it is also possible that in the end there be clusters with less than that number of observations because some were shared.

### Pros
- No need to specify the number of clusters
- Clusters of arbitrary shape can be discovered
- Noisy oservations are put aside
- Clusters are robust to outliers
- Needs two aprmeters $\epsilon^*$ and $min$ $points$ which both can be set by domain experts. (Also needs a distance function but shhhh)
### Cons
- Can be computationally intensive fasted algorithm as $O(nlogn)$ complexity.
In general $min$ $points$ $\ge p+1$ is good with larger values better for noisy datasets, we can also use $min$ $points$ $\ge 2p$ if we have a big dataset or repeated observations.
- Can not detect clusters with varying degrees of tightness
- ![Pasted image 20241212130059.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020241212130059.png) (Dudas Part 3, page 362)

The $\epsilon^*$ is harder to pick, but no matter the case, we should ensure that it is picked AFTER we selected our distance metric as it is much too easy to artificially get good results by going back and forth between distance metrics and it, leading to [[Data Dredging\|Data Dredging]].

The distance metric should be chosen for sound reasons and committed to.

## References
