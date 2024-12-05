---
{"dg-publish":true,"permalink":"/1-cosmos/dynamic-programming/","created":"2024-12-04T11:34:16.996-05:00","updated":"2024-12-05T09:32:59.843-05:00"}
---

202412041134
Status: #idea
Tags: [[Computer Science\|Computer Science]]
State: #awakened
# Dynamic Programming

At its inception it had nothing to do with programming (coding) but instead was understood as a mathematical tool to schedule things. Apparently it was only named like that because it was a cool name that got the higher ups (in the army I think it was?) to take it seriously even though fundamentally it was just math.

With time programmers learned of it and realized it was a powerful tool to solve a whole class of problems in computer science and it was co-opted as a [[Computer Science\|computer science]] staple.

## Principle
- There's a problem to solve that is composed of many identitical sub-problems (typically recursive in nature)
- Solving without taking that into considering leads to a **LOT** of repeated work and intractable algorithms.
- But smart solving can fix the issue and lead us towards performance.

The main idea is really just that.

There's two ways to go about it, either [[Tabulation\|Tabulation]] or its dual to [[Memoization\|Memoization]].

One goes bottom-up, the other goes top-down. They both make the same observation that a big problem with repeated subproblems would be inefficient to solve naively, they just go about in opposite ways. 


### Memoization vs Tabulation

| Question | Tabulation | Memoization |
|------------|--------------------------|--------------------
| How do they solve big problems | Bottom-Up Approach | Top-Down Approach|
|Uses extra memory? | Yes | Yes|
| How exactly? | Solves all the sub-problem from the smallest and then builds to the instance we care about | Recursively breaks the big problem into smaller ones and breaking those into smaller ones until it reaches a base case, then propagate upwards while saving the intermediate results |
| Computation Order | Iterative, starts form smallest sub-problems | Recursive, starts from the main problem and breaks downs |
| Initializing | Need to initialize the full table/array upfront | Lazy, caches as subproblems are encountered |
| Typical Impementation | Uses tabulation (array/table) | Typically uses a hashmap |
| Pros | Guaranteed to solve all subproblems, often more space-efficient | Much more intuitive, likely the first cost-cutting method one would think of. Memoization results are typically stored in a global state, so the more we call the function, the more efficient it becomes and will start giving $O(1)$ time complexities |
| Cons | Less intuitive, requires understanding the entire problem structure upfront and building from there. A new table must be built for each call to the function of the same size, if the complexity of the algo is $O(n^2)$, and we call it 10 times, even though we already computed it once we will need to do those $10n^2$ total |  Overhead from recursive calls, potential stack overflow. |

How fitting to represent all this information in a table if I do say so myself. Lol.

## Framework
![shot-2024-12-04_13-25-47.jpg](/img/user/3.%20Black%20Holes/Files/shot-2024-12-04_13-25-47.jpg)

## Why Dynamic Programming is Actually Great
Dynamic Programming often gets a bad rep as a difficult, galaxy-brain algorithm that requires a whole new method each and every time and for which tables need to be introduced often *seemingly* out of nowhere.

And actually fair enough. While it is really not that hard, and the core intuition of it is quite simple, the way it is often taught, without properly explaining the intuition or reasoning steps that leads to a given implementation often leads students feeling puzzled.

It does not help that the table/array approach that is often used largely disconnects the solution of a problem from the logic that is used to solve it to all but those with the deepest understanding of both its structure and the logic that induces said structure.

But guess what, dynamic programming is actually easy! (Except for every time I have to relearn it because I don't use it.)

Dynamic Programming is the rawest form of problem solving one can find in programming, and while it can be confusing, the path to solving these problems is pretty much always the same:
0. Identify you have a dynamic programming problem on your hands
1. Identify all your possible moves, and for each move identify the consequence (typically actions are forcing, so you need to consider what happens in each case)
2. Do this for all actions that can be taken until your logic loops back into essentially solving the same problem but smaller.
3. Identify the base cases, when can each action be taken and what to do if it cannot.
4. That's what you've been doing implicitly, but write a "naive" recursive algorithm that solves the problem. 

Bravo, you have already solved let's say 90% of the problem.
At this point, you have two options:
1. Either you implement [[Memoization\|memoization]] which will allow you to cache the results of those recursive calls keeping your logic the **exact** same. In Python, this can be done trivially easy by using the ```@cache``` decorator above your recursive function.
2. Or you convert your recursive method to an iterative one by considering the dependencies of each step (what do you need to know at step $i$ to proceed) and writing the code so that said values are computed ahead of time.
For some, the second option is what $DP$ is. This is patently false, rather it is an application of a method called [[Tabulation\|tabulation]] which is a specific type of $DP$ that utilizes the cache locality and efficiency of array-based structures for saving computations.

Fundamentally both [[Tabulation\|tabulation]] and [[Memoization\|memoization]] make use of caching, the different is that the former does so at a call level, needing to recompute said computations each time the function is called again, and the other at a global level so that once computed, it doesn't need to be computed again.

The time complexity of the two methods is typically the same when amortized, so which is best really depends of the problem at hand.

Here are a few write-ups where I solve some classic $DP$ problems in ridiculous details.
## My Write-Up Explanations of Standard Problems

[[1. Cosmos/Optimal Chain of Matrix Multiplication using Dynamic Programming\|Optimal Chain of Matrix Multiplication using Dynamic Programming]]
[[Floyd-Warshall Algorithm for All-Pair Shortest Path\|Floyd-Warshall Algorithm for All-Pair Shortest Path]]
[[0-1 Knapsack Problem\|0-1 Knapsack Problem]]
[Longest Common Subsequence (LSC)]
## References
[[Tabulation\|Tabulation]]
[[Memoization\|Memoization]]
#### Friggin Watch These
[DecodingIntuition's Part 1 ~ Amazing Video on Explaining DP](https://www.youtube.com/watch?v=gK8KmTDtX8E&t=11s)
[DecodingIntuition's Part 2 ~ How to make it iterative]

