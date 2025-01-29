---
{"dg-publish":true,"permalink":"/1-cosmos/floyd-warshall-algorithm-for-all-pair-shortest-path/","created":"2025-01-22T11:17:13.998-05:00","updated":"2024-12-06T21:05:08.838-05:00"}
---

**202412052155**
Status: #idea
Tags: [[Algorithms\|Algorithms]], [[1. Cosmos/Dynamic Programming\|Dynamic Programming]]
State: #nascient
# Floyd-Warshall Algorithm for All-Pair Shortest Path

When trying to find the shortest path to go from a vertex to another, we know of [[Dijkstra\|Dijkstra]] the algorithm that can give us the result in $O(NlogM)$ time complexity where $M$ is the number of edges and $N$ is the number of vertices.

But it falls short if we want to find that shortest path not starting from a single vertex as [[Dijkstra\|Dijkstra]] does, but rather to find for each vertex the shortest path that gives us the answer.

How do we do that? Well, hopefully, this is what we will be elucidating.

## The Setup
Graphs can be represented in various forms from the gross-looking and annoying-to-work-with edge list, to the elegant if memory intensive adjacency matrix. Then there's the sweet child in the middle, the adjaacency list which can be used as well.

For this algorithm though, we always start from the adjacency matrix. The reason is quite simply, for free, it gives us the initial most direct paths which exists from vertex $A$ to vertex $B$ and vice-versa.

Typically in said graphs, $0$ represents positions where no connections exist, on the other hand since each entry in the graph represents the "distance" from vertex $i$ to vertex $j$, one must be careful in how it is noted.

Typically we will use $\infty$ to represent any such entries because intuitively enough if no path exists from $A$ to $B$, the distance to it is infinite as I could never close it. The second thing is that the diagonal entries are 0m  we do not admit self-loops and even if we did we can easily reason that it would always take less time to go from $A$ to $A$ if we simply didn't do anything instead of taking some circular path that takes us around the block and brings us back.

These matrices will typically look a little something like this:
$$
\begin{bmatrix}
0 & 10 & \infty & 1 \\
6 & 0 & 3 & 7 \\
10 & \infty & 0 & 9 \\
15 & 2 & 7& 0
\end{bmatrix}
$$
Things to note
- All entries are positive, as you'd expect from dealing with distances
- $M[i,j]$ tells us the cost of going from $i$ to $j$. **NOT NECESSARILY SYMMETRIC**
- Diagonal entries are $0$ as going from $i$ to $i$ is free.
- Here, there is no way to go to vertex $2$ from vertex $3$ and likewise to go to vertex $3$ from vertex $1$, this is made clear by the $\infty$.

This is our initial matrix typically called $A^0$, as it tells us without passing through any auxiliary vertices, what are the paths that exist between my edges. This will be the input to our future function and contains all the information we need to get started.

Intuitively, what we are trying to do here boils down to for each possible vertices we could choose to include or not consider if passing by that vertex would shorten the path and compute the optimal combination of vertices to do it. 

The issue is straightforwardly this is not trivial, while it makes sense thatif the optimal path from $i$ to $j$ passes by $k$, then it follows that any path that further builds  from $j$ will also pass by $k$ (assuming it starts from $i$.)

But computing all the combinations possible for each vertex is not only not feasible, but it would also then be quite the task to derive the right path from it.

So how do we do?



## References
