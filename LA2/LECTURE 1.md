

We will be covering a lot of vector spaces and Matrix factorization.
In LA1, we worked in vector spaces of $F^n$ and solved SLEs for tasks.
We should define again vector spaces, also infinite dimensional vector spaces.

There is a difference between the definitions and properties of topics.
We will include more proofs.
We will discuss linear mappings.
Vector spaces are types of sets with more properties.

All linear mappings are matrices.

We define inner product / dot product.
For every 'entry' in a vector, we multiply it with its 'neighbor' multiple and sum the products.

Two vectors are orthogonal if the dot product is zero.
The normal of the vector, $|v| = (v \cdot v) ^ {\frac{1}{2}}$ 

Without analysis, we will explore inner products and normalization for finite dimension.

Let us discuss matrix factorization. It is simpler to understand more complicated matrices through a different, deconstructed view. Firstly, diagonizable matrices can be destructed into $A=SDS^{-1}$ 
D shares a spectrum with $A$, as well as the rank. It is very easy to check invertibility.

For second midterm, we will discuss QR decomposition ( $A=QR$ ) . (QR Algorithm)

Exists also SVD - singular value decomposition. Very strong decomposition.
Every rectangular matrix has an SVD decomposition. It uses all the previous theory.
Gives information about rank, etc.
Matrix is not necessary to be invertible, but we can define pseudo-inverse using SVD.
Editor's note: There can be non rectangular matrices..?


We want to define $F^{\infty}$ - all sequences such that the elements belong to it.
$F^{\infty} = \{(x_n)_n \in N : x_n \in F_n\}$ 
We want to define operations:
- $+ ~:~ F^{\infty} \times F^{\infty} \rightarrow F^{\infty}$
- $(a_n)_n+(b_n)_n = (a_n+b_n)_n$
- $\cdot ~:~ F \times F^{\infty} \rightarrow F^{\infty}$
- $\lambda (a_n)_n = (\lambda a_n)_n$
- Additive identity, zero vector.
- $\vec0 = (0,0,...)$ 


Let X be a set, and F be a field.
Let $F^X$ be all the mappings from $X \rightarrow F$ such that $f$ is a mapping.
- Vector addition $f,g \in F^X$
- (f+g)(x) = f(x)+g(x)
- Scalar multiplication $\lambda \in F, f \in F^X$
- $(\lambda f)(x) = \lambda f(x)$

Additive zero would just be zero as $0 \in F^X$
Editor's note: $F^X$ is a set of mappings. How is zero a mapping?
Outcome: It is not actual zero, it is simply the zero of the V, not the zero of the field. It is the additive identity. It is a map.
The zero map sends each X to the zero. $0: X \rightarrow F$

Every sequence is a mapping from the natural to the field.

Vector spaces require abstract thinking which we will explore.

Each polynomial is a mapping from $F \rightarrow F$ .
Thus, $P(C) \subseteq C^C, P(R) \subseteq R^R$
Let us now claim that these are vector spaces.
We can define vector addition and scalar multiplication for the two of these.
These should be simple as it is a map. i.e. $(p+q)(z) = p(z)+q(z)$
The zero map is just.. zero. zero polynomial.

Proposition
Let $V$ be a vector space over $F$. Then:
1. $V$ has a unique additive identity
2. Every vector in $V$ has a unique additive inverse.
3. For every $v \in V$, $0 \cdot v = 0$.
4. For every $a \in F, a \cdot 0 = 0$.
5. For every $v \in V, (-1) v = -v$.

First, proof by contradiction. Consider two additive inverses $0,0'$
Since it is the additive identity, by definition:
- $0' = 0+0'$
- $0 = 0' + 0$
Then, $0 = 0' + 0 = 0'$ so the additive identities are the same $\implies$ unique.

Second, again by contradiction, assume $v$ has two additive inverses, $w, w'$ .
According to add. inv. def. $w+v=0$ and $w'+v=0$
Thus, $w=w'+0$ and so $w=w' \implies$ unique add. inv. 