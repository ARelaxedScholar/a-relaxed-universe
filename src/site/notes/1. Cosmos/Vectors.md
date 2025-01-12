---
{"dg-publish":true,"permalink":"/1-cosmos/vectors/","created":"2025-01-11T14:27:28.117-05:00","updated":"2025-01-11T14:36:23.145-05:00"}
---

202501111427
Status: #idea
Tags: 
State: #nascient
# Vectors

Rigorously, a vector is any component of a [[1. Cosmos/Vector Space\|vector space]]. They are mathematical objects which can be added among each other to yield another object of the same time, and that can be scaled by an element of some field in such a way that they yield another vector.

When we look at tensors and start delving into that world, we realize that for any vector space that behaves as we expect, there exist an intrinsically related vector space where the inhabitants of that world despite being "vectors" in the definition sense no longer are the same type of mathematical objects.

If when thinking of vectors you think mathematical object that you can add and multiply together, then that dual space contains functions (linear maps to be precise) which takes the first objects as inputs. The interesting part is that linear maps are functions, and linear maps can be added and scaled, hence they are vectors as well. Still, they are not the traditional vectors and instead are named [[1. Cosmos/Covectors\|covectors]] to highlight their subordinate relationship with the first set.

That said, the traditional vectors are what we call [[1. Cosmos/Contravariant\|Contravariant]] tensors, as their *components* vary in a fashion opposite to the *basis* vectors. This means that to write a vector using a new basis, while the first instinct might be to use the forward transformation (transformation that bring old basis to new basis), you must instead use the backward transformation (transformation that bring new to old) because and I can't state this strongly enough—the components of a vector do the OPPOSITE of the basis of its vector space.


## References
