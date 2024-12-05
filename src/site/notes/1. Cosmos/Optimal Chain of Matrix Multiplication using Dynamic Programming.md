---
{"dg-publish":true,"permalink":"/1-cosmos/optimal-chain-of-matrix-multiplication-using-dynamic-programming/","created":"2024-12-04T14:46:13.381-05:00","updated":"2024-12-05T14:26:33.523-05:00"}
---

202412041446
Status: #idea
Tags: [[Algorithms\|Algorithms]]
State: #nascient
# Optimal Chain of Matrix Multiplication using Dynamic Programming

One of the key problems to understand when dealing with $DP$ as understanding its structure is a masterclass into how one should think about these problems in general.

For solving $DP$ problems, the best approach is typically just to try on a small exemplary, find a formula as soon as possible, and in an academic context prove that the formula is correct, on an exam pray that your thing is correct and then build the logic from there.

## The Setup: Part 1
With three matrices $A, B,C$ multiplied as follows $ABC$, there are **two** ways the operation could go, they are the following:
$$
(AB)C=A(BC)
$$
This is due to the associativity property of matrix multiplication.

It goes without saying that for matrix multiplication to work we need the dimensions to match, so while we have three matrices with two dimensions each (so in total $6$), the order of the matrix multiplication cuts two degrees of freedom so-to-speak and enforces that two of those 6 be the same.

To be clear:
$$
\begin{align}
&A: d_a\times d_b\\
&B: d_c\times d_d\\
&C: d_e\times d_f\\
&\text{but since } AB \text { and } BC \text{ are given we know that}\\
&d_b = d_c, d_d=d_e
\end{align}
$$
So if we relabel them such that $$d_a=d_0, d_b=d_c=d_1, d_d=d_e=d_2, d_f=d_3$$
We get 4 dimensions in total such that:
$$
\begin{align}
&A: d_0\times d_1\\
&B: d_1\times d_2\\
&C: d_2\times d_3\\
\end{align}
$$
So we see that the dimensions of the inner matrices are enforced as soon as we start talking matrix multiplication. Good stuff!

## The Setup: Part 2
But why do we care?
Well, you must have guessed by now, but the order in which we multiply the matrices while equivalent in terms of the answer it gives is **NOT** equivalent in terms of the number of operations it will take.

An example is worth 10,000 words so let's take one example.
$$
\begin{align}
&A: d_0\times d_1\\
&B: d_1\times d_2\\
&A\times B
\end{align}
$$
Well here, $A$ has $d_0$ rows and $d_1$ columns, and $B$ has $d_1$ rows and $d_2$ columns. Since the inner dimensions are the same, they are compatible for multiplication.

Now let us take multiplication as our basic operation to compare complexity.

Observe that matrix multiplication is the same as taking the dot product of the rows of the first matrix, with the columns of the second matrix (hence why we need the inner dimension to match).

In this case, this means for each pairwise (row-column) vector we have $d_0$ multiplications, that is one multiplication to do per position within a vector. (Please convince yourself of that by writing it on paper.)

We should know from probability theory, that when we want to see the total number of ways to do something, when the actions are independent, we use a product.

So in the first matrix $A$, we have $d_0$ rows, that is $d_0$ vectors that can and WILL be used for a dot product to obtain an entry in the resulting matrix.

In the second matrix $B$, we have $d_2$ columns, each compatible for a dot product with the rows of $A$.

As a result, there are $d_0\times d_2$ possible $row-column$ matchings, correct? Along with giving us the number of entries in the resulting matrix, this tells us how many times we will need to do a dot product.

And for each of these dot products, we will need to do $d_1$ multiplications (the number of components within one vector.)

So in total we have $d_0\times d_1 \times d_2$ multiplications to do for a 2 matrix multiplication.

Take a matrix $A$ with $4$ rows and $3$ columns, and a matrix $B$ with $3$ rows and $2$ columns, that is in total:
$$
4 \times 3 \times 2 = 24 \text{ multiplications}
$$
To obtain the matrix $AB$ (this order is enforced by the dimensions.)

So if we take $ABC$ now, and retake the general dimensions we had earlier:
$$
\begin{align}
&A: d_0\times d_1\\
&B: d_1\times d_2\\
&C: d_2\times d_3\\
\end{align}
$$

It means that we can either take:
$$
(d_0 \times d_1 \times d_2) +  (d_0\times d_2 \times d_3) 
$$
or 
$$
(d_0 \times d_1 \times d_3) + (d_1 \times d_2 \times d_3) 
$$

See how these expressions are not the same?
For fun, let us set $d_0=1, d_1=2, d_2=3, d_3=4$

Then we get:
$$
18 \text{ vs } 32
$$
In this example where: $A$ has $1$ row and $2$ columns, $B$ has $2$ rows and $3$ columns and $C$ has $3$ rows and $4$ columns, it is clear that the order:
$(AB)C$ is preferable to the order $A(BC)$, since the latter takes 177.7% more operations!

Which is why, it is so crucial to find the optimal order for matrix multiplication before starting. Matrix multiplications already being so costly, if we end up doing double or triple the amount of work required to get the same result, we are really shooting ourselves in the foot.

Here the difference might not seem substantial since we had small matrices, but for real life problems the matrices might be a few hundreds or thousands of dimensions, so these discrepancies means a few order of magnitudes of difference.

So how do we attack that?

## The Algorithm

I want you to ponder about what we just did, we compared the solution of two level below where we currently were, and then chose from the minimum of the two.

Since the operation was elementary, it can be easy to miss what we did, but the logic is exactly what we'd want to do in practice. Exhaustively test all the approaches, and choose the order which gives us the minimum.

The second thing that might not have been clear from the example, but intuitively should make sense is that if I have a multiplication of $4$ matrices to do, the order which gives the minimum will itself be dependent on the order which gave the minimum on the smaller chains of $1,2,3$ matrices.

This property is what we call the [[Optimal Substructure\|Optimal Substructure]] property which is a property of problems for which it can be shown that recursively applying an algorithm that works on the bigger problem to the smaller problem will give the optimal answer because fundamentally they are the same problem just at varying sizes.

But if we just test all cases, how is it different from raw bruteforce? Well that's the trick, dynamic programming by building incrementally from the bottom-up is able to compute all the required building blocks of a step $k$ of a solution only once, as a result it minimizes the number of computations to do.

If we take our example here, notice what we did:
We have two formulas:
$$(d_0 \times d_1 \times d_2) +  (d_0\times d_2 \times d_3) $$
and 
$$
(d_0 \times d_1 \times d_3) + (d_1 \times d_2 \times d_3) 
$$
And we want the minimum of the two so really, we want:
$$
min \begin{cases}
(d_0 \times d_1 \times d_2) +  (d_0\times d_2 \times d_3) \\(
d_0 \times d_1 \times d_3) + (d_1 \times d_2 \times d_3) \\
\end{cases}
$$
Let us call this term $C[1,3]$ for the cost of multiplying across from matrix $1$ to matrix $3$.

This is nice, but it is not generalizable yet, two formulas, that's gross.

If the above term is defined as the cost of multiplying across from matrix $1$ to matrix $3$, then we can recall from the work above that for the first equation:
$$(d_0 \times d_1 \times d_2) +  (d_0\times d_2 \times d_3) $$
the first term is really the cost of $C[1,2]$.

While in the second equation, the second term is the cost of multiplying second matrix across to three (based again on what we did above) so $C[2,3]$

If we rewrite the minimization formula above we get:
$$
min \begin{cases}
C[1,2] +  (d_0\times d_2 \times d_3) \\
C[2,3]+ (d_0 \times d_1 \times d_3)  \\
\end{cases}
$$
This is cool, but we do not yet have something generalizable after all, it seems that in the second equation, there are terms related to the first and vice-versa, it'd be well if we could introduce a term that does not change a thing, that is effectively $0$ all the time, but that still gives us enough leeway to be able to relate terms together...

Let us observe that taken the degenerate chain of matrix $A$, where the chain contains a single element, the cost of multiplying across from $1$ to $1$ would effectively be $0$ as there's nothing to multiply.

If we use the notation we just introduced we get $C[1,1]=0$, right? Since we have a single matrix in the chain and therefore its position is $1$. 

So yet again if we backtrack to the work we did before and try to add context-aware zeroes, we see that for the first term we can see the problem as the summation of $C[1,2]+C[3,3]$ because we multiply across the third matrix alone, yet again this term is $0$.

On the other hand, if we take the second equation, we multiply across the first matrix to the first matrix (we leave it alone) and add the cost to the cost of multiplying across from the second matrix to the third matrix so that we have $C[1,1]+C[2,3]$.

$$
min \begin{cases}
C[1,2]+C[3,3]+  (d_0\times d_2 \times d_3) \\
C[1,1]+C[2,3]+ (d_0 \times d_1 \times d_3)  \\
\end{cases}
$$

Now we have something that is better, as we see numbers which are related both in the cost problems and the multiplications of the current dimensions.

Intuitively, we are summing the cost of obtaining the two sub-matrices we are multiplying and adding to that the cost of the actual multiplication of said matrices. This is hard to grasp in words so take the following example with $5$ matrices.
$$
ABCDE = (A)(BCDE) = (AB)(CDE) = (ABC)(DE) = (ABCD)(E)
$$

Well each of these pairings have a cost to obtain right?
The one on the left $(A)$ and the one on the right $(E)$ have cost $0$ since we didn't have to multiply to obtain them, but say we have $AB$ or $CDE$, or even $BCDE$ before even getting to the cost of the full matrix, we must get the cost of these matrices.

The beautiful thing with [[1. Cosmos/Dynamic Programming\|dynamic programming]] is that we don't care, remember, we solve the general problem (being aware of the recursion) and then think about how to order the resolution of the problems so that we can in term solve everything efficiently.

From the work we've done we know that the solution will be:
$$
C[ABCDE] = min \begin{cases}
C[A]+C[BCDE]+  d_{Arows}\times d_{A columns}=d_{(BCDE)rows} \times d_{(BCDE)columns} \\
\vdots  \\
C[ABCD]+C[E]+  d_{(ABCD)rows}\times d_{(ABCD) columns}=d_{Erows} \times d_{Ecolumns} \\
\end{cases}
$$

And as you can see, recursively, we'll need to find $C[BCDE]$ and $C[ABCD]$, where you'd write the pairings exhaustively as we did for $ABCDE$ and break those up.

Now if we use our notation, where instead of referring to mass of matrices by their name, we refer to them as slices of a list containing them, then $C[ABCDE]$ is perfectly equivalent to:
$$
C[1,5]=min \begin{cases}
C[1,1]+C[2,5]+  d_{0}\times d_{1} \times d_{5} \\
\vdots  \\
C[1,4]+C[5,5]+  d_{0}\times d_{4} \times d_{5} \\
\end{cases}
$$

You should convince yourself of this by looking at the dimensions of the resulting matrix and which matrices in the chain force said dimension and realizing that based on our notation since the beginning the number of rows of the first matrix IS $d_0$.

This is much better, we have a something that almost looks like a formula, the final step is to progressively abstract the repeated part.

First, we see that for $C[1,5] => C[i,j]$ on the left side, we will replace all the places where we consistently see the number appear by $i,j$:

So:
$$
C[i,j]=min \begin{cases}
C[i,1]+C[2,j]+  d_{i-1}\times d_{1} \times d_{j} \\
\vdots  \\
C[i,4]+C[5,j]+  d_{i-1}\times d_{4} \times d_{j} \\
\end{cases}
$$
So, the first detail to note is that $d_0$ is $d_{i-1}$ because it is directly linked to the number of rows of whatever matrix we are referring to with $i$.

The $1$ on the first row, and $5$ on the last row were not changed by $i$ or $j$ because clearly, they vary. It would be an error to say that they are tied to the $i$-th matrix or the $j$-th matrix.

So let us add a new variable $k$, the $k$ will represent the matrix where we make our split. This is consistent with the example above, as $k=1$ means that the first matrix is alone and then we multiply from the second matrix across to the last, on the other hand if $k=j-1$, then that means that the last matrix is alone, and we multiplied across from the first matrix to that penultimate matrix! Observe that we are not doing anything magical here, we are simply taking an example and then turning it to a formula.

Let us observe a few key things:
- $k$ is allowed to be $i$, since we can leave the first matrix alone and must start from the end.
- $k$ must be less than $j$ since, for the second term we go from $k+1$ to the end, since $k+1$ can at most be $j$, it follows that $k$ cannot be $j$.
- $k$ cannot be less than $i$. This is simply because $k$ represents a matrix BETWEEN the first and the last.

So with all that in mind, we can simplify and finally write a general formula that is:
$$
C[i,j]=min_{i\le k < j} \big \{
C[i,k]+C[k+1,j]+  d_{i-1}\times d_{k} \times d_{j}\big \}
$$
Amazing! We have finally worked through a general formula. 
So how to actually use this thing, you might ask?

Well glad you asked, this is the next part.

## So what do I do with this?

Well, you are a patient guy/gal if you've read through this.
You can give yourself a pat on the back. Hopefully now the construction of this algorithm, at least theoretically, is limpid.

Now how do we use it.

Earlier I mentioned how in $DP$ we start by finding the recursive formula, and then concern ourselves with how to best order the resolution of problems to get an answer.

For $DP$ you will systematically use either an array, or a table, or a few of these depending of the complexity of the problem as you will be incrementally building to the solution.

Here we actually use $2$ tables (matrices).
One will keep track or which $k$ gave us the best cost, and the other will be recording the actual cost at each step.

Using these two matrices we will be able to know which order gives us the best cost in terms of number of multiplications, and then how many multiplications that "best" is.

If you are keen, you might have realized something interesting already.
When we have a single element in the chain $C[A]=C[1,1]$ then there are no splits to do, and there is no cost associated.

When we have two elements $C[AB]=C[1,2]$, there is a split to do, but that split is forced in the middle, so we only have one operation to do, and using the formula we had, we'd get:
$$
(C[A]=0)+(C[B]=0)+d_{Arows} \times (d_{A_columns}=d_{B_rows}) \times d_{Bcolumns} =
$$
$$
d_{Arows} \times (d_{A_columns}=d_{B_rows}) \times d_{Bcolumns} 
$$
And then as we when we went to $5$ elements in the chain, there were $4$ possible matchings.

We will be using that property. Since matrix chains with more elements will be using the cost of matrix chains with less elements, we can compute iteratively the cost of the chains with $1$ element, and then $2$ and then $3$ all the way to the chain with $n$ elements which will just be the full matrix.

At this point, thanks to the prior work, we will have everything we need to build it up.

### Breakdown of the Algorithm

0. Start by creating two matrices one that we will call $K$ (for hopefully obvious reasons) and another that we will call $O$ as it will contain the number of operations for the **optimal** paths. These two matrices will be $M\times M$ where $M$ is the number of matrices in the chain. Initialize them with zeroes.
	- We will only utilize the upper half of those two matrices (upper half being from the diagonal up)
	- We should already have an array $D$ which contains the dimensions of the matrices conform with our current notation.
1. Consider all the $C[i,i]$ along the diagonal, realize that these constitute all the costs of multiplying a matrix across itself, which is zero. Both $K$ and $O$ are unchanged.
2. Consider now all the pairings where we consider chains of two matrices, in other terms they are those where the difference $j,i$ is $1$. We are now filling the diagonal right above the diagonal, at this point we are not yet using the $min$ since we only have $1$ choice per entry, for each chain of $2$ we simply fill with the cost obtained in the appropriate location in the matrix. For example, the cost of $C[1,2]$ which is of multiplying across from the first matrix to the second matrix will be put in $O[1,2]$, or the first row and second column. The $K$ matrix will be filled with the single entry $k$ that is used at that level, for that very same example, $K[1,2]$ is filled with $k=2$.
3. Now we stored the cost and $k$ of all those chains built from two matrices, we can now attack those made of three matrices, for the first time we have to select a minimum. In $O[1,3$] we will need to refer to $O[1,2], $O[3,3]$ and $O[1,1]$ and $O[2,3]$ and the appropriate dimensions from the $D$ array. If you ever get confused just remember what these values represent!
	- Once we computed both costs, at either $k=1$ and $k=2$, we put the $k$ associated with the minimum value in $K[1,3]$ and the minimum value in $O[1,3]$.
	A similar logic will be used for everything else.
4. From there, just keep filling up diagonals, by diagonals, until you get to the $O[n,n]$ which will tell you the minimum number of operations.
5. Enjoy!?!
Congratulations, if you understood all of that, you got the algorithm and its intuition on lock!

Looking at $O[M,M]$ gives you the least number of multiplications to complete the multiplication, and $K[M,M]$ tells us after which matrix to put the first parentheses. This represents the first "optimal" recursive split.

Then from there we know that we have to sub-products to consider, that is the product from the first matrix to the $k-th$ matrix, and then from the $(k+1)-th$ matrix to the $M-th$ matrix.

These optimal $k's$ are also inscribed in the $K$ table at respectively:
$$
K[1,k]
$$
and 
$$
K[k+1, M]
$$

We keep recursively checking like this until all elements are broken down to single matrices. We want something like this:
![shot-2024-12-04_19-13-53.jpg](/img/user/3.%20Black%20Holes/Files/shot-2024-12-04_19-13-53.jpg) (These are taken from my algorithm professor Nejib Zaguia's Lecture Notes, thank you! <3)

Here is some python code if you are more programmatically minded with a bonus recursive implementation:
Note that since we derived the pattern already, the task is really just to write code for it.

#### Iterative Implementation, basically the logic we outlined above
```python
# This is not part of the ALGO, but needed for 
# numpy to be available in my Obsidian environment
#import micropip
#await micropip.install('numpy')

# Actual ALGO
import numpy as np
def find_min_cost_tabular(D):
	M = len(D)-1
	
	# hang on, it's gonna be 
	O, K = np.zeros((M,M), dtype=float), np.zeros((M,M), dtype=int)

	# We can skip the diagonal step since already zeroed
	for chain_length in range(2, M+1): # gotta consider length M as well
		# consider all possible i for a given length
		for i in range(M-chain_length+1):
			j = i + chain_length - 1

			# initialize to huge value
			O[i][j] = np.inf

			for k in range(i,j):
				cost = (O[i][k] + O[k+1][j] +
						D[i] * D[k+1] * D[j+1])
						
				# Update to the minimum cost and store K
				if cost < O[i][j]:
					O[i][j] = cost
					K[i][j] = k
	
	# see, everything is 
	return int(O[0][M-1]), K

# Test
cursor = 1 # we need index 1 to select cost of matrix 2
tuple_optimal, tuple_k = find_min_cost_tabular((1,2,3))
list_optimal, list_k = find_min_cost_tabular([1,2,3])
print(f"The min cost of matrix multiplicaton for dimensions [1,2,3] is : {tuple_optimal} multiplications")
print(f"The min cost of matrix multiplicaton for dimensions [1,2,3] is : {list_optimal} multiplications")

print(f"And the k-Matrices are: {tuple_k}")
print(f"Wait, but are both equivalent?: {tuple_k == list_k}")
print("Damn right they are.")

print("So, we can pass a list or a tuple here, this is foreshadowing.")
```

See how clean this looks, there's some ugliness due to the fact we need to mix floats and infinity. From this $K$ matrix we'd need another algorithm that is $log(M)$ to read the splits off the $K$ matrix, but this article is already almost $4k$ words, so I think you'll forgive me for leaving it out.
### Hahaha, recursion goes brrr.

```python
from functools import cache
# Recursive
@cache
def find_min_cost_memoized(D):
	M = len(D)-1 # number of matrices

	# no cost if there's a single matrix
	if M <= 1:
		return 0

	all_costs = [
		find_min_cost(D[:m+2]) + 
		find_min_cost(D[m+1:]) + 
		D[0] * D[m+1] * D[M]
		for m in range(M-1)]
	
	min_cost = min(all_costs)
	return min_cost

print(f"The min cost of matrix multiplicaton for dimensions [1,2,3] is : {find_min_cost_memoized((1,2,3))}")

print("Note that we gotta pass a tuple since @cache requires inputs to be hashable")
```
See how easy this looks? Furthermore see how all we did was transform the mathematical formulae we had into code (adjusting for $0$-indexing shenanigans?)

This is dynamic programming, more specifically [[Memoization\|memoization]]. It's disadvantage is that on the first few runs for big values it will be exceedingly slow as nothing is stored in cache yet, but as time progresses, the amortized complexity will converge to whatever the [[Tabulation\|tabulation]] approach gives, since in essence that's kinda what we are doing.

Now you might be wondering how do we retrieve the optimal solution? 

Please sit down. (Yes, because you were definitely reading this standing up.)

We can't. At least not with this implementation.

Memoization is great when all we care about is one state, more specifically it is great when we treat each function as... a function, a mathematical function that is. 
This means no side effects! 

Realize that caching here allows us to skip running a function given that result is already in memory, our recursive implementation would likely require some data structure (likely a list) being assed down) and progressively filled with the optimal $k$'s.

This is not doable consistently and would give meaningless paths (or even none) making our algorithm unusable.

It's in cases like these where an iterative implementation imposes itself, knowing when to go for the intuitive simplicity of [[Memoization\|memoization]] or the robustness and velocity of [[Tabulation\|tabulation]] is an art.

## And the Time Complexity?

If you understood the rest, this is the easy part.
Let's look at the matrix $O$, in the first column we fill in $1$ value if we count the $0$, in the second column we fill $2$ and this increases as you'd expect until when we reach column $M$, the full column is filled with $M$ values.

This gives us:
$$
1+2+3+\dots+M = \frac{M(M+1)}{2} \in O(M^2)
$$

Now, we must consider the $K$ matrix as well.
For each column that we will in $O$, we must consider $M-1$ different values of $k$, the number of said values of $k$ always being $1$ less than the number of matrices in the chain.

So, if we were to write the complexity in long we have:
$$
0(1)+1(2)+2(3)+\dots+(M-1)(M)
$$
Where for each $k$ we compute the cost that would be obtained for said $k$ and then pick the one which yields the minimum cost. 
Here we are trying to find an upper bound, so we can observe that since all of these terms are products and all these numbers are positive, the following holds:

$$
0(1)+1(2)+2(3)+\dots+(M-1)(M) < (M-1)(1)+(M-1)(2)+\dots+(M-1)(M)
$$


Note that the $RHS$ is equal to:
$$
(M-1)(\sum_{i=1}^Mi)=(M-1)(\frac{M(M+1)}{2})=\frac{M^3-M}{2} \in O(M^3)
$$

Boom! So as we see the complexity of the algorithmic is cubic in the number of matrices in the chain and provides us with both the least number of multiplications and how exactly to get it.
## References

[[1. Cosmos/Dynamic Programming\|Dynamic Programming]]
[Fantastic Video by Abdul Bari which explains it all](https://www.youtube.com/watch?v=_WncuhSJZyA)
