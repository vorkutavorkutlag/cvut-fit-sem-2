
We were looking at $U$ as a subspace of $R^n$ or $C^n$.
We wanted to find orthonormal bases $\mathcal E$ for $U$.
Coordinate of a given vector w.r.t $\mathcal E$.
For given $v$, we compute the closest point in $U$ to $v$.

When we are in coordinate vector spaces, the inner product is the dot product, that is important.
As in, $<w,v> = w \cdot v = \overline v_1 w_1 + ... + \overline v_n w_n = w^*v$

We will define the inner product for polynomial vector spaces $P(R), P(C)$.
It is defined using integration, but we won't need it, instead, using a formula that is derived from the integration.

We can define $p(x)q(x) = (a_0 + ... a_1x^n)(b_0 + ... + b_mx^m)$
It is actually quite similar to the general formula for inner product of matrices.
$$\int_0^1 p(x)q(x)dx = \int_0^1\sum_j \sum _i a_{ij}b_{ij} x^{i+j}dx$$

So we define $<p,q>=a_0b_0 + \frac{a_0b_1 + a_1b_0}{2}+\frac{a_0b_2 + a_1b_1 + a_2b_0}{3} + etc.$

The problem is, to show that it is an inner product.
We don't need to know that exactly.

It is useful not only for polynomials, but in general is useful for infinite dimensional entities and other functions with them.

...

We will solve some problems.

Find an orthonormal basis of $P_2(R)$.
Note that the standard basis is not orthonormal by the definition we have.
$<1,x>=\frac{1}{2}, <x,x^2>=\frac{1}{4}, etc.$ Meanwhile they have to be equal to $1$ or $0$.

General fact is, if $B$ is a basis of $(V, <\cdot, \cdot>)$, then apply G-sch to $B$ to obtain an orthonormal basis.
So, we should apply G-sch to the standard basis of $P_2(R)$.

// Why are some bases orthonormal in some spaces, but not orthonormal in other spaces which are isomorphic to them?
// Why not take every orthonormal basis to an orthonormal basis?
// Is it possible to create such mapping with this specific definition in $P_2(C)$

The general formula we use, again, for inner product is $<p,q>=a_0b_0 + \frac{a_0b_1+a_1b_0}{3}+\frac{a_1b_2+a_2b_1}{4}+\frac{a_2b_2}{5}$ 

Or, simpler, I think I should just integrate the product of the polynomials. :/

We have standard basis $(1,x,x^2) \in P_2(R)$
$e_1 = \frac{1}{||1||} = 1$

$e_2' = x - <x, 1>1 = -\frac{1}{2} + x$
$e_2 = \frac{e_2'}{||e_2'||}$ where $||e_2'|| = \sqrt{<x-\frac{1}{2}, x - \frac{1}{2}>} = \frac{1}{2\sqrt3}$
Thus, $e_2=\sqrt 3 (2x-1)$


$e_3' = x^2-<x^2, e_2>e_2$ 
$e_3 = \frac{e_3'}{||e_3'||}$
...

G-sch is not exclusive to coordinate vector spaces as you may see.
It works for any inner product space, with any definition of an inner product.
See how I said an inner product, not the inner product.

The other definition we can come up with is $$<p, q> = \int_{-1}^1 p(x)q(x)dx$$
Then, the standard basis is orthonormal, as expected. 
We are NOT, absolutely NOT using it in our problems, as we were given the $\int_0^1$ definition, but just know that this exists and is much nicer to look at and think about in my opinion. 
Every orthonormal basis in coordinate inner product vector space will be sent to an orthonormal polynomial bases.

Actually this is false. $1, x^2$ are not orthonormal.
It might be impossible. `@_@`

...

When we have an orthonormal basis, finding a vector w.r.t it is really simple.
We have no need in solving an SLE. Rather,
$$[q]_{\mathcal E} = \begin{bmatrix}<q,e_1> \\ ... \\ <q, e_n>\end{bmatrix}$$
Write the formula, and compute one of them.

...

...

...

We also talked about inner product space with $M_{m,n}(C)$
Then, we can define $<A,B> = tr(B^*A)$ 
Additionally, we have property $tr(AC) = tr(CA)$