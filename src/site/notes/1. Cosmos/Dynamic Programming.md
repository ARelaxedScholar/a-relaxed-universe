---
{"dg-publish":true,"permalink":"/1-cosmos/dynamic-programming/","created":"2024-12-04T11:34:16.996-05:00","updated":"2024-12-04T14:43:17.279-05:00"}
---

202412041134
Status: #idea
Tags: 
State: #nascient
# Dynamic Programming

At its inception it had nothing to do with programming (coding) but instead was understood as a mathematical tool to schedule things.

With time programmers learned of it and realized it was a powerful tool to solve a whole class of problems in computer science and it was co-opted as a [[Computer Science\|computer science]] staple.

## Principle
- There's a problem to solve that is composed of many identitical sub-problems (typically recursive in nature)
- Solving without taking that into considering leads to a **LOT** of repeated work and intractable algorithms.
- But smart solving can fix the issue and lead us towards performance.

This concept is a dual to [[Memoization\|Memoization]] which makes the same observation that a big problem with repeated subproblems would be inefficient to solve naively except that they go in opposite ways. By that I mean that one builds iteratively bottoms up (DP) while the other gnaws recursively and top-down...

### Memoization vs Dynamic Programming

| Question | Dynamic Programming | Memoization |
|------------|--------------------------|--------------------
| How do they solve big problems | Bottom-Up Approach | Top-Down Approach|
|Uses extra memory? | Yes | Yes|
| How exactly? | Solves all the sub-problem from the smallest and then builds to the instance we care about | Recursively breaks the big problem into smaller ones and breaking those into smaller ones until it reaches a base case, then propagate upwards while saving the intermediate results |
| Computation Order | Iterative, starts form smallest sub-problems | Recursive, starts from the main problem and breaks downs |
| Initializing | Need to initialize the full table/array upfront | Lazy, caches as subproblems are encountered |
| Typical Imlementation | Uses tabulation (array/table) | Typically uses a hashmap |
| Pros | Guaranteed to solve all subproblems, often more space-efficient | Much more intuitive, likely the first cost-cutting method one would think of. Memoization results are typically stored in a global state, so the more we call the function, the more efficient it becomes and will start giving $O(1)$ time complexities |
| Cons | Less intuitive, requires understanding the entire problem structure upfront and building from there. A new table must be built for each call to the function of the same size, if the complexity of the algo is $O(n^2)$, and we call it 10 times, even though we already computed it once we will need to do those $10n^2$ total |  Overhead from recursive calls, potential stack overflow. |

How fitting to represent all this information in a table if I do say so myself. Lol.

## Framework
![shot-2024-12-04_13-25-47.jpg](/img/user/3.%20Black%20Holes/Files/shot-2024-12-04_13-25-47.jpg)


## My Write-Up Explanations of Standard Problems

[[1. Cosmos/Optimal Chain of Matrix Multiplication using Dynamic Programming\|Optimal Chain of Matrix Multiplication using Dynamic Programming]]
[[Floyd-Warshall Algorithm for All-Pair Shortest Path\|Floyd-Warshall Algorithm for All-Pair Shortest Path]]
## References
