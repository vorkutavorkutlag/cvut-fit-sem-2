
Today, Gram-Schmidt, Inner products

Given a vector space, it's natural to consider how two vectors relate to each other in terms of closeness of direction.
We want a function that tells us how closely related two vectors are.

Given a vector space over a complex field.
$$<\cdot, \cdot> : V \times V \to C$$

It is any mapping that satisfies the following properties:
- $<v,w> = \overline{<w,v>}$  - Conjugate Symmetry
- $<cv,w> = c<v,w>$ - Homogeneity in first slot
- $<v+x,w> = <v,w> + <x,w>$ - Additivity in first slot
- $<v,w> ~\geq~ 0$  - Positivity
- $<v,v> = 0 \iff v = \vec0$ - Definiteness
It is possible to use these with the conjugate to introduce conjugate homogeneity in the second slot, and conjugate additivity in the second slot.

The inner product in $C^n$ is the dot product.
$$<\cdot, \cdot> C^n \times C^n \to C$$ $$<v,w> = \sum_i^n a_i\overline b_i$$

// importantly, conjugate the second vector.
// then it works with the linear conjugacy in the second slot, and normal linear in the first slot.

Not every coordinate space has a dot product. It must be over field $C$.

For polynomials, we have the definition:
$$<\cdot, \cdot> P(C) \times P(C) \to C$$ $$ \int_0^1 p(x)\overline{q(x)} dx$$

Consider we have a matrix $A \in M_{m,n}(C)$.
The conjugate transpose, i.e. the adjoined, defined $A*$ is defined s.t.
$(\forall i \in [1,n])(\forall j \in [1,m]) (A^*)_{ij} = \overline{A_{ji}}$
Basically, the transpose and the conjugate.
Important property includes $(A^*)^*=A$.

Doing an inner product, we do not get something in the vector space like previous times, we get a number that can tell us about the relation between them.
Now, in $M_{m,n}(C)$
$$<A,B> = tr(B^*A)$$

This is also intuitive, as this evaluates into $\sum_j^n \sum_i^n a_{ij} \overline {b_{ij}}$

Notice how it's similar to the vectors.

// higher degree Tensors could be triple sums maybe?

...

The inner product is not the final step. It's a necessary step though.

