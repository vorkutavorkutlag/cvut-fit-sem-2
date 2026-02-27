
If you are here then it means you have survived LA1. 
The subject is more loose than LA1.

Marzieh snitched on us. We have a hard problem allegedly. Distinguishing between a definition and properties of the object concerned by the definition.
We will talk a lot about definitions.
Then we will have examples about inf. dim. and fin. dim. vector spaces.
Vector space trivia.

We want to remove the pacifier of $F^n$  or $F^{\infty}$. Be more abstract.

Can anyone say what a vector space is?
A set equipped and closed under vector addition, scalar multiplication (with which we need a field).
We can consider $(R^2, R, +, \cdot)$ - what we add, and what we multiply by.
The addition is happening in $R^2$, the multiplication is happening between $R, R^2$.
Think of this as two structures that were glued together.

We have some good properties. $c_1,c_2 \in R$, $w, v \in R^2$
- $(c_1+c_2)v = c_1v+c_2v \in R^2$
- $c_1(v+w) = c_1v + c_1w \in R^2$

Note that in the first, the addition is happening in field $R$, and the addition in the second is happening in vector space $R^2$.
We distinguish them mentally.

These equations are trivial, but they are axioms. These are axioms of distributivity.
It is easier to understand the structure than remembering all the axioms. 
We box it in our head. Vector addition, Scalar multiplication, Distributivity, Commutativity...

A vector subspace is a subset of the vector space. It inherits the operations from the vector space, but it must be closed under these operations. Every element should have an inverse, have the identities.
The scalar multiplication cannot be changed, it is under the same fields, we inherit it from our "upper-space".

A subspace of $R^2$ for example is $\{\begin{bmatrix}a_1 \\ a_2\end{bmatrix}\ \in R^2 : a_1 = a_2\}$   
It is closed under addition, scalar addition works similarly, so we're safe.
We have an algorithm if something is a subspace, we check for these three things, and that we don't have an empty set, and that we have a zero.
There is a linearity that we need to be a subspace. For example, non-linear changes such as $a_1=a_2^2$ would not hold.

Consider infinitely long tuples/sequences of real numbers.
Let's take the set of these sequences, such that $a_i \in R, i \geq 1$ 
Consider two elements, as in, two infinite sequences.
I want to define an addition for them.
The addition that we have is entry-wise. We would define it:
$(a_1,a_2,a_3,...)+(b_1,b_2,b_3,...)=(a_1+b_1,a_2+b_2,a_3+b_3,...)$
Though this is not enough, we have to define some other qualities for the vector space. For example, we need a zero, and an additive inverse. Which we have!
We are missing associativity and commutativity. 
How do we show $a+b = b+a$?
We can use the commutativity on our field, $R$, and show that $a_i+b_i = b_i+a_i$ for every entry in both $a+b, b+a$ respectively.
We can do the same with associativity in the same way ($a+(b+c) = (a+b)+c$)
We didn't know that addition in the infinite field is commutative, but we know that addition in $R$ is commutative, so we can prove it.

This object can be called an element $\in R^{\infty}$ .
An infinite dimensional vector space - if for any integer $n$ we cannot find a list that spans that vector space. That is characterization, not definition.
We will get to the definition later.

$L = (v_1,..,v_n) \in V$ is a spanning list iff
$span(v_1,...,v_n) = V$
Meaning also, ($\forall w \in V,~ \exists a_1,...,a_2 \in F) ~w=a_1v_1+...+a_nv_n$ 

The definition of linear independence iff the only LC that equals zero vector is when all the scalars are equal zero.

Some sources will define the basis as a spanning list such that you can uniquely express any vector in the vector space, but Marzieh wants us to say that it is simply a list that is spanning and is LI.

If we look at polynomials also, we also have the property $(p+q)(x) = p(x) = q(x)$ 
Polynomial addition may be defined $\sum_{i=0}^n(a_1+b_i)x^i$

$P_3(R)$ is the polynomial space of $R^3$

LI is a question of addition, not multiplication, so we can answer questions such as "is this list of matrices LI?".
The standard basis for every $F^n$ is $(1 ... 0 0 0), (0 1 ... 0 0 0) ... ( ... 0 0 0 1)$
The standard basis for $P_n(F)$ is $(1, x, ..., x^n)$ so the dimension is $n+1$.
The standard basis for $M_{n,m}(F)$ is like the rest, all zeros except a single 1, for every entry in the matrix.

A finite dimensional subspace of an infinite dimensional subspace exists, and for example $\{(a_n) \in R^{\infty} : (\forall i \geq 10) a_i = 0 \}$

The quick idea of isomorphism is that there are two notions. Somehow preserves the structure. We preserve the core structures of the space and that we have a bijection.
We will go more into it when we have linear maps.

$V$ is inf. dim. iff $(\forall m \in N)(\exists v_1,..,v_m \in V)$ s.t. $(v_1,..,v_m)$ is LI.
$V$ does not admit a finite spanning list. Above is definition, this is equivalence.
$P(R)$ is the set of all polynomials.

Some inf. dim. subspaces of $R^{\infty}$ include $\{a_n \in R^{\infty} : a_1 = 0\}$, $\{a_n \in R^{\infty} : a_{2k} = 0, k \geq 1\}$ 

Also, can look at all the functions from some set into your field, denoted $F^X$
Vector is anything that can be in a vector space, but it is not necessary require to be coordinate spaces.

Functions on a certain interval. We can add, multiply by scalars, so we can get a vector space of functions. These would be considered vectors, but not coordinate vectors.

Everything can be represented as a part of an infinite dimensional subspace, so it's useful.

Coordinates with respect to a basis in the abstract form are

How many possible polynomials are there in $P_3(Z_7)$? $7^{3+1}$

Is $(x+1, x^2+2, x^3+3)$ LI? Check if every polynomial is in the span of the list without that polynomial.
We can express that in basis $(1, x, x^2, x^3)$ as $$\begin{bmatrix}1 &2&3 \\ 1 & 0 & 0 \\ 0 & 1&0\\0 &0&1\end{bmatrix}$$
