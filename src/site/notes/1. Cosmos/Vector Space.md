---
{"dg-publish":true,"permalink":"/1-cosmos/vector-space/","created":"2024-12-09T15:31:49.120-05:00","updated":"2024-12-10T12:18:39.192-05:00"}
---

202412091531
Status: #idea
Tags: [[1. Cosmos/Linear Algebra\|Linear Algebra]]
State: #nascient
# Vector Space

So vector spaces can be understood as an extension of [[Group\|groups]] in [[1. Cosmos/Group Theory\|Group Theory]] where instead of having one operation, there are two operations:
- addition over the elements of the space
- multiplication by scalar
- a well-chosen set of properties (from Group Theory) over both operations so that algebra holds

If we have these properties on a space, then for all intent and purposes in the context of [[1. Cosmos/Linear Algebra\|Linear Algebra]], we have a vector space, and the things that exist within it are [[Vector\|vectors]], irrespective of whether they are an arrow in space, a set of matrices, or functions.

A vector space is always defined over some space $V$ which contains the elements that we call vectors, and a [[Field\|field]] $F$, typically clear in the context from which we take the scalars.
Once, these are are clear, we need these rules to hold, there are 8 in total:
- Closure under addition of vectors s.t $a,b \in V$ then $a+b\in V$  (inherited from [[1. Cosmos/Group Theory\|Group Theory]])
- Closure under scalar multiplication so that $\lambda \cdot v$ for any vector in the space and for any scalar $\lambda$ yields a vector within the space (this is logical from the above.)
- Associativity of addition operation, typically a given, but if we have custom operations we need our "addition" to be associative (inherited from [[1. Cosmos/Group Theory\|Group Theory]])
- Commutativity of addition operation, also typically a given, this is a property of the addition operation itself.
- Presence of an additive identity (inherited from [[1. Cosmos/Group Theory\|Group Theory]])
- Presence of an additive inverse (also inherited from [[1. Cosmos/Group Theory\|Group Theory]])
- Existence of Multiplicative Identity (you catch the drift now)
- Distributive properties:
	- *Distribution of elements to scalars $a(x+y)=ax+ay$*, where $a\in F$ and $x,y \in V$
	- *Distribution of scalars to elements $(a+b)x = ax+bx$*, where $a,b \in F$ and $x\in V$.

In general, many of these are clear and inherited from the space we're working on, especially if the space is $\mathbb{R}$ and $\mathbb{C}$, $F$ is often $\mathbb{R}$ but in general is $F$ is $\mathbb{C}$.

Typically the ones that need verification are the closure properties, the verification of whether an identity exists within the space, and then the presence of inverses.

## Subspaces
Very often we are working within a space that we know is a vector space, but are interested in a subset of the vectors within it.

For linear algebra to be valid and not give unexpected results, we want the confidence that using our standard operations on the vectors will yield other vectors of interest. In other words, we want the subset of interest to be a vector space in its own rights.

Thankfully, once we know that we are working in a vector space, many of these properties are already a given as they already were verified and the operation is valid, so all we need to do is to check that the following points:
- Are the identities still in the subset?
- Does every element in the subset have its inverse
- Is the space closed?

If these three things are verified, then we know we have a subspace as the rest is inherited from the superspace. This is analogous to the [[Subgroup Test\|Subgroup Test]] and in fact has a very similar name "Subspace Test".

It can be easily be shown that take $U$ and $W$ be two subspaces of $V$ then:
- $U \cap W \subseteq V$, always. Where here $\subseteq$ is abused to mean subspace.
- $U\cup W\nsubseteq V$  in general. In fact if $U \cup W \subseteq V$ then it can be shown that $U \subseteq W$ or $W \subseteq U$.

While we do not have to work with matrices, we very often do and when we do, there are three key spaces that are derived from the matrix and which are subspaces exist in $F^{m\times m}$.

These key subspace are:
- [[Null Space\|Null Space]]
- [[Column Space\|Column Space]]
- [[Row Space\|Row Space]]

Another important one that is not quite a space of the matrix itself, and in fact is the null space of another matrix but that is still integral to our matrix $A$, and that space is the [[1. Cosmos/Eigenspace\|Eigenspace]] which is the space where the vectors exist.

### Span Theorem
If you feel too cool for school and don't want to show explicitly that space respects certain set of rules, it is often more convenient to simply express the vectors in the space as a span.

If you can show that a space can be expressed as a span of some vectors, then the space is a vector space.

This can be demonstrated by showing that the belonging rule here would be being the result of some linear combination of the vectors in the span, and by virtue of that, every property we care about holds.

## References
