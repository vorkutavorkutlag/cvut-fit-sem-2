
If $T \in L(v,w)$ then show $T(\vec0) = \vec0$
Then, if a mapping s.t. $T(\vec0) \neq \vec0$ then it is not linear.

Do not use injectivity, kernel, etc. here!  - We are talking about linearity not bijectivity.

$T(\vec0) = T(\vec0 + \vec0) = T\vec0 + T\vec0$      using linearity
Add $(-T\vec0)$ to both sides.
$\vec0 = T\vec0$.

...

$T: \mathbb{M}_2(\mathbb{R}) \rightarrow \mathbb{R}$
$T \begin{bmatrix}a & b \\ c & d \end{bmatrix} = a^2+b+2c+d$  
We can find scalar counter example.
$T: \mathbb{R}^2 \rightarrow \mathbb{R}^2$
$T\begin{bmatrix}a \\ b \end{bmatrix} = \begin{bmatrix} |a| \\ -3b \end{bmatrix}$
We can find negative scalar counter example.

Don't use arbitrary $a, b, c, d$ for counter-examples, we can instead just use numbers we choose to show a single counter example.

$Z_p$ is the set of equivalence classes $\{[a]_p : a = 0,..,p-1\}$

All linear map must map zero to zero.

When proving for polynomials in $P(\mathbb{C})$, we don't look at degrees, we can assume they have the same degree and fill the lesser degree polynomial's higher coefficients with zeros.
Then, pairing and proving linearity becomes much easier.
As in, $T(\lambda p_1 + p_2) = ... = \lambda Tp_1 + Tp_2$


Construct a linear map from $P_4(\mathbb{R}) \rightarrow R^\Omega$
We use the fact from lecture note:
If dimension of $V$ is finite, fix a basis $B = (v_1,...,v_n)$ of $V$ and arbitrary vectors $w_1,...,w_n$ in $W$. Then there is unique ($\exists !$) $T:v \rightarrow w$ s.t. $T(v_i) = w_i$
Basis for $P_4$: $(1, x, x^2, x^3, x^4)$
Vectors in $R^\Omega$: $w_0=(1,1,0,...), w_1=(-1,1,0,....), w_2=(0,0,1,0), w_3=(1,0,-1,0,1,0,...), w_4=(0,0,1,0,0,1,0,...)$
Just for linear map, they can be entirely arbitrary for constructing. For isomorphism we need to make a basis, but this can be arbitrary.

Then, $T1=w_0, Tx=w_1, Tx^2 = w_2, Tx^3 = w_3, Tx^4=w_4$

The $w$'s are LI $\iff$ map will be injective
You should know the proof.

We can pick something similar to the standard basis.
$w_0 = e^{(1)} = (1,0,0,...)$
$w_1=e^{(2)} = (0,1,0,0,...)$
etc.
$w_0,...,w_5 \in R^\Omega$
This is one of the LI lists, but there are plenty more. If we shift everything forward, it will still be LI and thus injective.

And for surjectivity?
Fundamental Theorem of Linear Algebra.
Suppose $V$ is f. dim. vector space, and $W$ is arbitrary vector space.
If $T \in L(V,W)$ then:
- $ran(T)$ is finite dimensional.
- $dim(V) = dim(ker(T)) + dim(ran(T))$ 

Assume it is surjective.
// Note that the kernel is zero due to injectivity.
But, $dim(V) = 5$, which is less than infinity $(dim(ran(T)))$ 
So we have found the contradiction.
Therefore there is no surjective map $P_4(R) \rightarrow R^\Omega$.


...

Adding any vectors to a spanning list, still keeps it a spanning list.
We use that when finding a surjective linear mapping from $V$ to $W$ when the dimension of the former is higher than the dimension of the latter.
We'd need to add vectors more than the basis, but it's fine, given that fact.

It is always better to use the more basic theorems, such as the fundamental theorem.
Yes, it is possible to say that there can exist no LI list of length greater than the dimension, but that statement is based on the fundamental theorem.

Will have similar problems in test (check your p\*per notebook!)

Construct a linear mapping:
- $\mathbb{R}^\Omega \rightarrow P(\mathbb{C})$
- $P(\mathbb{C}) \rightarrow \mathbb{R}^\Omega$

$T(a_0, a_1, a_2,a_3,...)=a_0+a_1x+...+a_4x^4$

A polynomial must converge, it must be finite. We should not use arbitrary $n$, we should give an example of a linear map, not be arbitrary.

Side-note: $P(\mathbb{C})$ has an infinite basis of an infinite sum. It is infinite in a sense, but $R^\Omega$ is a different kind of infinity. Every element can be written as an infinite sum.

$T(a_0+a_1x+...+a_nx^n) = (a_0,a_1,...,a_n,0,0,...)$

We cannot find an isomorphism between $P(\mathbb{C})$ and $\mathbb{R}^\Omega$ . 
It should take spanning set to spanning set and LI set to LI set.
Very complicated topic, I am lost. Christian B. Hughes I evoke your name.

...

// Remember definition of LI (zero-scalars).

// Dimension of range always less than or equal to dimension of codomain.

...

Christian B. Hughes I evoke your name.
Christian B. Hughes I evoke your name.
Christian B. Hughes I evoke your name.

$\textreferencemark$  

Later, theorems about isomorphism....
