---
{"dg-publish":true,"permalink":"/1-cosmos/singular-value-decomposition/","created":"2024-12-14T09:04:46.410-05:00","updated":"2024-12-14T19:03:11.175-05:00"}
---

202412140904
Status: #idea
Tags: 
State: #nascient
# Singular Value Decomposition

## A Little Motivation
Ok so [[Eigenvalue Decomposition\|Eigenvalue Decomposition]] is one of those really cool things about matrices, they are convenient because matrices are [[Linear Maps\|Linear Maps]] but these linear maps can be really hard to interpret.

After all as general transformations, they are as follows:
$$
L:R^n\mapsto R^m
$$
They take vectors from $R^n$ and then map them to $R^m$. 

The advantage with [[Eigenvalue Decomposition\|Eigenvalue Decomposition]], and more specifically decomposition of matrices which are [[Symmetric\|Symmetric]] is that by the [[Spectral Decomposition Theorem\|Spectral Decomposition Theorem]] if a matrix is [[Symmetric\|symmetric]] then two things are guaranteed:
- It will have a full set of [[Eigenvalue\|eigenvalues]] (which is not special this is always the case)
- It will have a eigenvectors which are orthogonal (or can be chosen to be so.)

This is really special because Eigenvalue decomposition gives us the following equation:
$$
A=P\varLambda P^{-1}
$$

Where the columns of $P$ are the eigenvectors of $A$, but if they are orthogonal (actually orthonormal) then it means that $P^{-1}=P^T$ simply $P^TP$ become a dot product between these columns, which is going to give the Kronecker-delta of the square norm of each [[1. Cosmos/Eigenvector\|eigenvector]] $e_i$, and we normalize it so that the norm is $1$, then everything works out.

To make what we did clear we generally rewrite it as follows:
$$
A=Q\varLambda Q^T
$$


This is cool for a very powerful reason, given an orthogonal matrix (a matrix with orthonormal columns,) then its effect on any vector is summarized by a clean rotation. No scaling or otherwise. 

To understand the transformation that a matrix applies to a space a good trick that I happened to learn from 3B1B is to check what happens to a set of vector that is easy to understand, that set is the standard basis.

It shouldn't be too hard to see that, if we take the application of $Q$ on the standard basis (which we will compact into a matrix as follows):
$$
\begin{bmatrix}
1 & 0 & \dots & & 0 \\
0 & 1 & & & &\\
\vdots &  & \ddots & & \\
\\0&0&\dots&0&1
\end{bmatrix}
$$

We solve it in general, so this is a $n\times n$ matrix, without having to do anything you know that this matrix is exactly $I_n$.

In other words:
$$
QI_n=Q 
$$
Which implies that each vector of the standard basis lands on the corresponding eigenvector within $Q$. This can be seen for a specific example:
$$
\begin{bmatrix}
1 & 1 \\
1 & -1
\end{bmatrix} \begin{bmatrix}
1  \\
0
\end{bmatrix}= \begin{bmatrix}
1  \\
1
\end{bmatrix}
$$

The first element of the standard basis "picks out" the first column of the matrix, or more accurately is mapped to that first column. 

The orthogonal matrix $Q$ would rotate the space in such a way that the standard basis aligns with the [[1. Cosmos/Eigenvector\|eigenvectors]]. It shouldn't sound far-fetched then that $Q^T$ that is also $Q^{-1}$ will be the transformation that takes the eigenvectors and map them to the standard basis. (Just apply the logic in reverse.)

The last thing to understand for this explanation is that [[Diagonal Matrices\|Diagonal Matrices]] are essentially scaling matrices. They take each dimensions of the vector they take and scale it by the corresponding entry on the diagonal.

Thanks to that we can represent the transformation of ANY symmetric matrix as the application read from right to left of:
$$
V^T=V^{-1} (rotate) \to \varLambda (scale)\to V(rotate)
$$

Or in other words, all symmetric matrices when applied to a space $R^n$ will:
1. Will rotate the space such that the eigenvectors (which remember are orthogonal) align with the standard basis (where the standard basis is exactly the columns of $V^T$ as we've shown above.)
2. Scale the space in each direction according to the eigenvectors of $A$.
3. Rotate the space (back) so that the eigenvectors are pointing where they used to.

Any matrix can be understood in those terms... no (for now) it's specifically for any symmetric matrix.

Indeed, to say nothing of rectangular matrices that you can't even begin to diagonalize, square matrices that happen to be diagonalizable will not have orthogonal vectors (if they are real) or if they are complex can only have them if they happen to be [[Normal Matrices\|Normal Matrices]] in such a way that this nice interpretation applies only to a subset of a subset of all possible matrices.

What if you could do that to every matrix irrespective of its dimensions, if its diagonalizable, if it has a full set of eigenvectors, etc.

Cue in [[1. Cosmos/Singular Value Decomposition#So Intuition?\|SVD]] which is often understood as the crown jewel of [[1. Cosmos/Linear Algebra\|Linear Algebra]].


## So Intuition?
Let's backthrottle a little bit, when we have an orthogonally diagonalizable matrix (which is the same as saying $A$ is symmetric, a cool thing we can do is realize that if:
$$
A = Q\varLambda Q^{T} \implies AQ = Q\varLambda \text{, just multiply } Q \text{ on the left}
$$

The $LHS$ of the consequence is akin to multiplying all at once a group of vectors $\{q_1, q_2, \dots, q_n\}$ by the matrix $A$, the $RHS$ by the fact we have a matrix multiplied on the **left** by a [[Diagonal Matrices\|diagonal matrix]] tells us that the **columns** (rather than the rows) are being scaled.

This tells us what we already know, but the vectors in $Q$ are eigenvectors of $A$ so that when $A$ is applied on them, they are simply scaled.

"So... why did we do that?" I hear you ask.

The answer is simple, while the above relation seems trivial, this is exactly the beautiful thing we are trying to generalize. 

What are the key properties of the elements displayed above?
- The matrix $Q$ is orthogonal (or unitary if it s complex)
- The columns of $Q$ form an orthogonal basis of $R^n$ and $R^m$.
- The matrix $\varLambda$ is diagonal and all it does is scale the vectors on the $RHS$.

The fact that $Q$ is orthogonal after all, orthogonal matrices have really nice and simple effects on a space (a rotation) if it wasn't the breakdown the decomposition of effects we had above wouldn't work.

The fact that the columns form an orthonormal basis is a consequence of the fact $Q$ is orthogonal, and is a fact we might miss if not careful, but this is the [[Eigenbasis\|Eigenbasis]] of $A$ which is not a trivial set of vectors.

The fact that $\varLambda$ is a scaling matrix is also important, because if it was anything more than that then the nice geometric intuition of rotation, scaling, rotation that is so key of symmetric matrices wouldn't work. After all this work we might find it's not possible (spoiler: we won't) but we're trying to port the nice interpretation of the effects of symmetric matrices on space to all possible matrices, hence trying as much as possible to enforce that is key.

So now let us take a general matrix $A$ with dimension $m\times n$. As we see, it is no longer (necessarily) square, it is no longer (necessarily) symmetric.

We'd like if possible to find a set of vectors, such that when multiplied by the matrix $A$, they are scaled equal to another set of vectors and are scaled. We'd like moreover that these set of vectors are not any set of vectors, but a set of vectors that are mutually orthogonal. So we map from a set of orthogonal vectors to another set of orthogonal vectors... This sounds difficult, doesn't it?

For no particular reasons, I will call the set of vectors that we start with $V$ and I want it mapped to $U$. We know on the right we will have a scaling matrix with only entries on the diagonal, so yet again for no particular reason we choose the Greek letter sigma $\varSigma$ to represent it. I hope you realize I could have called them $A,B,D$ or whatever. Let's also say that out of convenience we're going to sort the numbers along the diagonal from largest to smallest\*.

This gives us:
$$
AV=U\varSigma
$$

This looks like a simple equation, but remember $A$ is not (necessarily) square, as a result for this to work we need to ensure the dimensions match properly.

Let's start from the left, while $V$ surely has the first dimension $n$ ($n$ rows) it might not be obvious how many columns it should have. Just recall that our goal is to make it so $A$ is decomposed into the product of these three matrices, and that to cancel $V$ on the right we need to multiply to $V^T$ and it becomes clear that $V \in R^{n\times n}$.

Now for the left, we know that $U$ has to have it's first dimension as $m$ since that's what the dimension of the product $U\varSigma$ would give. We also know that $\varSigma$ has to have $n$ columns because it has to be able to take $V^T$ on its right and $V^T\in \mathbb{R}^{n \times n}$ 

Finally the middle dimension needs to agree... if we say that $\varSigma$ is an analog to $\varLambda$, it would be natural to say that $\varSigma$ is square. But then we lose the nifty interpretation of $U$ has a rotation matrix which is one of the key feature of the original. Since that's important, we enforce that $U$ is square and under those parameters, $\varSigma$ is forced so we can say that the dimension of all our matrices are as follows:
$$
\begin{align}
A&:m\times n\\
V&: n\times n\\
U&: m\times m\\
\varSigma &: m\times n
\end{align}
$$
*Note that for $\varSigma$ we could have chosen the dimensions differently, but this is a natural way to proceed considering our setup.*

Because of what we said the matrix $\varSigma$ might be rectangular!

Looking back at the equation:
$$
AV=U\varSigma
$$
We realize that while it looks inoffensive, quite a lot is happening. First, we said that

The matrix $V$ has $n$ columns, each with $n$ entries as to match with $A$, these columns are also orthonormal. This mean if nothing else, $V$ is an orthonormal basis for the space that the row of $A$ occupies that is $\mathbb{R}^n$. Please take a minute to ponder on why this is true.

On the the $RHS$, the matrix $U$ also has orthonormal columns, and there's $m$ of them each with $m$ entries. In other words, $U$ forms an orthonormal basis for the space which houses the columns of $A$ that is $\mathbb{R}^m$.

In our quest to generalize the nice properties observable in the symmetric matrix case, if it succeeds will give us the means to find a specific orthonormal basis of the row space of $A$ which when multiplied by $A$ gives another orthonormal basis, this time in the column space of $A$. What..?

Yes. This is metal.

Now, there's one point that we conveniently swept under the rug, which is the fact that $A$ might not be a full rank matrix, in other words the columns of $A$ does not span the space in which they live. Hold that thought, it will all work out in the end.

## How do we do that though?
Excellent question, how do we find a magic (orthogonal) set of vectors $V$ who span the space in which the rows of $A$ live (note that is not necessarily the [[Row Space\|Row Space]]) and that also happen to when multiplied with $A$ give another set of magic vectors $U$ that span the space where the columsn of $A$ live (also not necessarily the [[Column Space\|Column Space]] itself.)

This might seem like an impossibly hard task, and if we wandered blindly, it might as well be, but we can be smarter than that, let's use what we know about the matrices we have. Assuming that such a set of vectors exist, all the following is true:
$$
\begin{align}
AV &= U\varSigma\\
A&=U\varSigma V^{-1}\\
&= U\varSigma V^T \text{, since } V \text{ is orthogonal}
\end{align}
$$

So now we have $A$ defined as a product of matrices, thanks to the intepretation we have above, we already have an idea of how any matrix $A$ can be interpreted, but how the f?%k do we find the right thing?

Let's stop to think about how symmetric matrices are beautiful, and how all we are looking for essentially comes for free if we have symmetric matrices. After all, we do map a set of vectors unto another set of vectors just scaled.

It'd be nice if somehow we could make $A$ symmetric...

Well, while we can dream about that, we can do the next best thing. Create a matrix related to $A$ that happens to be symmetric, after all as long as the matrix we create include $A$, we can use the equation we just found and maybe work out something.

For many of you, the idea of "related" matrix that is symmetric lit up many light bulbs, if it didn't that's fine. Just realize/recall that by theorem any matrix multiplied by its transpose is [[Symmetric Semidefinite\|Symmetric Semidefinite]] and further a [[Symmetric Positive Definite Matrix\|Symmetric Positive Definite Matrix]] if $A$ is full rank. The proof is left to me in another note.

This means that if we multiply with $A^T$ on the right, we get this symmetric matrix
$$
AA^T
$$
and if instead we do it on the **left** we get this symmetric matrix
$$
A^TA
$$.

### Case $A^T$ on the right
And by the equation we wrote above:
$$
\begin{align}
AA^T&= (U\varSigma V^T)(U\varSigma V^T)^T\\
&= U\varSigma V^T~V\varSigma U^T\\
&= U\varSigma \varSigma^T U^T \text{, since  } V^T=V^{-1}\\
&= U\varSigma^2 U^T \text{, note } \varSigma^2  \text{ is } n\times n\\
\end{align}
$$

Wow! The columns of $U$ are nothing more than the eigenvectors of $AA^{T}$. Since $U$ is the matrix on the left of the matrix decomposition, these eigenvectors are typically called the *left* singular vectors.

Not only that we get what the values of our diagonal matrix $\varSigma$ are for free, they are the square root of the [[Eigenvalue\|eigenvalues]] of $AA^T$. 

### Case $A^T$ on the left
I could skip it, but since I am writing in Latex I can copy-paste stuff.
$$
\begin{align}
A^TA&= (U\varSigma V^T)^T(U\varSigma V^T)\\
&= V\varSigma U^T~U\varSigma V^T\\
&= V\varSigma^T\varSigma V^T\text{, since  } U^T=U^{-1}\\
&= V\varSigma^2 V^T \text{, note } \varSigma^2  \text{ is } m\times m \\
\end{align}
$$
So we see that the columns of $V$ are actually the eigenvectors of $A^TA$. Since $V$ is on the left in the $SVD$ product, they are typically called the right singular vectors.

But wait a minute, the center matrix is the same as we'd expect $\varSigma^2$ and logically it has the same values, but there's a potential size mismatch...

Even though this might be confusing, this is the first step towards a really nifty fact $A^TA$ and $AA^T$ have the same eigenvectors. Even though the eigenvectors themselves are different.


Now at this step, it wouldn't hurt to take a break. In pretty much one go, we solved all our problems.

We have a form:
$$
A=U\varSigma V^T
$$
such that the effects of each can be isolated:
- The matrix $V$ is a rotation which occurs in the input space, it aligns the standard basis to the eigenvectors of $A^TA$. Accordingly, $V^T$ rotates so that the eigenvectors fall on the standard basis.
- The matrix $\varSigma$ is now more than a scaling matrix. It still takes in vectors from the input space, but it applies two transformations at once: it erases/add a dimension, then scale the remaining components. In other words, the matrix $\varSigma$ single-handedly acts as the portal between dimensions.
- Finally, $U$ align those scaled vectors in the output space so that the standard basis of the new output space is now aligned with the eigenvectors of $AA^T$.

Boom!

Note that if $A$ is not a full-rank matrix, during the eigenvalue finding stage, we will find as many eigenvalue as the rank and the rest will be zeroes. In other words, if $A$ and $A^T$ lack the eigenvectors to span $R^n$ and $R^m$ respectively, then $AA^T$ and $A^TA$ will "borrow" so to speak from each null spaces (we will then need to orthogonalize them.)

But that's fine since if you remember your linear algebra well, there's a space that is by definition always perpendicular to the column space of a matrix that allows us to find an orthonormal basis of the space, and that is the [[Null Space\|Null Space]] (proof of why it's orthogonal in the Null Space note.)

Since we'd lack vectors to span the row space as well (since the dimension of [[Column Space\|Column Space]] and [[Row Space\|Row Space]] are the same) we'd also need to fill it, but recall that the [[Row Space\|Row Space]] is nothing more than the column space of $A^T$, and so we can fill the remaining vectors with the [[Null Space\|Null Space]] of that matrix!

So that is to say that $V$ which forms an orthonormal basis of the space in which the rows of $A$ live will either be a basis for the rows of $A$ itself, if it has full rank or a combination of a basis both the row space $A$ and the null space of of $A^T$.

On the other hand, $U$ will be either all a basis of the column space of $A$, or likewise a combination of the basis of the column space of $A$ and the null space of $A$.

## SO WHAT!?

Well glad you asked. SVD along with being the crown jewel of [[1. Cosmos/Linear Algebra\|Linear Algebra]] is one of the tools with the most applications spanning from:
- [[1. Cosmos/Principal Components Analysis (PCA)\|Principal Components Analysis (PCA)]] in Data Science and [[1. Cosmos/Machine Learning\|Machine Learning]]
- Image Compression ([[Low-rank Approximations\|Low-rank Approximations]])
- Solving Least-Squares in Ill-Posed Systems
- Etc.


## A Nice Bonus Before Leaving
Right now, the way we are doing it, we need to find both $AA^T$ and $A^TA$, find their eigenvales and eigenvectors, normalize them and whatnot.

Wouldn't it be nice if we could somehow use the work done in one cases to find the eigenvectors in the other?

It doesn't sound ridiculous that it should be possible, and in fact, no it's not.

First start by realizing that the eigenvectors of the former are the columns of $U$, while the latter are the columns of $V$.

Then realize that:
$$
A = U\varSigma V^T \iff AV=U\varSigma  
$$

Now, this might not be obvious yet, but if you recall how we started all of this, the matrix $\varSigma$ is a diagonal matrix, hence when multiplying it on the right it scales the columns!

As a result, if we want to unscale the columns to retrieve $U$ itself, all we need to do is to do the column scaling to the left side that would cancel the scaling applied by the matrix $\varSigma$.

That is:
$$
AV\varSigma^{-1}=U
$$
where $\varSigma^{-1}$ is nothing more than the matrix of the reciprocals of the singular values.

It shouldn't be too hard to convince yourself that:
$$
\varSigma^{-1}U^TA=V^T
$$
from which when taking the transpose we get:
$$
A^{T}U\varSigma=V
$$
which is to die for!

Whenever working on solving these problems, we can solve for whichever side is easier to solve and then compute easily the other matrix using what we already solved.

## What's missing
Well for this entire note, I have assumed that we were dealing with real matrices, what would that look like in the complex case? Not much different honestly. Everything pretty much works out the same way, but I'll do it later for practice as it has important consequences for specific forms of matrix decomposition like the [[Polar Decomposition\|Polar Decomposition]].



## References
