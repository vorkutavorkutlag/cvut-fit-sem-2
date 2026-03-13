Previously we had examples of infinite dimensional vector spaces.
Sum/Direct Sum of subspaces to produce new subspaces.

#### Linear Maps

After talking about the vector spaces, bases, LI, spanning and so on, we talked about matrices. It was the second part of LA1, about matrices, and we want to say that these are special cases of linear maps.

There is an analogy between sets and vector spaces.
Finite cardinality, finite dimensional, etc.
Mappings between sets...

Linear maps are from vector spaces $v, w$ under the same field.

$A \in M_{m,n}(F)$ 
We talked about if $v \in F^n$ then we can have $Av \in F^m$.
We define this multiplication.
We can look at every vector in $F^n$ as a matrix of size 1.
This matrix multiplication is like a map.

It is a linear map from $F^n$ to $F^m$ doing $v \rightarrow Av$
These are vector spaces on $F$.

What properties does a linear mapping $T_A$ have?
- $A(v+w) = Av + Aw ~~~~~...~~~~ T_A(v+w) = T_A(v) + T_A(w)$ 
- $A(\lambda v) = \lambda Av ~~~~~...~~~~ T_A(\lambda v) = \lambda T_A(v)$
- $(\forall v,w \in F^n) (\lambda \in F)$

A map is called linear if it satisfies these properties.
Additivity (preserves vector add.), Homogeneity (preserves scalar mult.).

Note also that the addition $v+w$ is in $F^n$, but the additions $T_A(v)+T_A(w)$ are additions in $F^m$.

We use the notation $Tv$ instead of $T(v)$.

Consider matrices, and consider linear mappings between vector spaces, we know that for every matrix $A$ we can associate a $T_A$ vector mapping.
We want to look if we can define all the notions of matrices for linear mappings in a general manner, for example, determinant. 
Kernel, range, transpose of a matrix can be defined for the linear mapping.

If we restrict ourselves to finite dimensional vector spaces, there will be correspondence between every linear mapping and a matrix (one-to-one bijection).

We have a convention, that $V, W$ are vector spaces or same field $F$.
If one of them is finite dimensional, we will emphasize. Otherwise, arbitrary.
$L(V,W)$ is the set of all linear mappings from $V \rightarrow W$.
In the case that $V=W$, we also denote $L(V,W)$

For example,
$T: V \rightarrow W$, then $Tv = \vec0$   ($\vec0 \in W$)
We also have $T(v+w) = 0 = 0 + 0 = Tv + Tw$
Then again $T(\lambda v) = 0 = \lambda 0 = \lambda Tv$
We use the abstract theory of vector spaces. $0+0 = 0, ~~~~ \lambda \cdot 0 =0$
We call the map that sends everything to zero, the zero. We can also denote $T$ as $0$.
Be careful to differentiate all the $0$'s depending on the context. Field, Vector Space, Mapping, can all be denoted by zero..

If $A \in M_{m,n}(F)$ is the zero matrix, then $T_A$ is the zero mapping $F^n \rightarrow F^m$.
If $A \in M_n(F)$ is the identity matrix, then $T_A$ is the identity map $F^n \rightarrow F^n$.
Naturally, it sends every $v \rightarrow v$.
Denoted either $id_V$ or $I_V$. For example, $I_{F^n}$ 

Let us define $T: P(C) \rightarrow P(C)$
Then, $T(P)$ is a polynomial.
Now we define $T(p)(x) = xp(x)$.
For example, $T(x+1) = x(x+1) = x^2+x$.
...We can find some examples which are not linear...

$T(p_1+p_2)(x) = x(p_1(x) + p_2(x)) = xp_1(x) + xp_2(x) = T(p_1)+T(p_2)(x) \rightarrow T(p_1+p_2) = Tp_1 + Tp_2$
Therefore, these have the additivity quality.
Two polynomials are the same when for every $x$ they result in the same output.


A backward shift is...
$T(a_1,a_2,a_3,...) = (a_2,a_3,...)$
We omit the first one, and "push" all of them to the front.
The forward shift... $T:F^\infty \rightarrow F^\infty$
We don't omit the last one as we don't have a last one. We add zero in the beginning.
$T(a_1,a_2,a_3,...) = (0, a_1, a_2,a_3,...)$

Not all subsets are subspaces, and in the same way, not all mappings are linear.
For example, any mapping like $T(\begin{bmatrix}v_1 \\ v_2 \\ v_3\end{bmatrix}) = \begin{bmatrix}v_1^2 \\ v_2 + v_3\end{bmatrix}$ 
We show it by the same properties. Additivity, Homogeneity.

Other examples with polynomials include $T:P(R) \rightarrow P(R)$
$T(a_0 + a_1x +...+a_nx^n) = a_0^2$
For example, $T(1)+T(x-1) = 1 + (-1)^2 = 2$ but $T(1+x-1)=0$

$T0 = 0$ due to linearity and additivity.

There is a systematic way to producing linear mappings.

Proposition states.
Let $V, W$ be vector spaces over $F$. Assume that $V$ is finite-dimensional, with basis $B = (v_1,..,v_n)$ and no assumptions for $W$. We have $w_1,...,w_n$ in $W$.
Then, there exists a unique $(\exists !)$ linear mapping $T:V \rightarrow W$ such that $Tv_i = Tw_i$ 

Construct a map $T:V \rightarrow W$ satisfying above.
We need to define the value of $T$ at any $v \in V$.
We now use the concepts of the basis.
Let $v \in V$. Since $B$ is a basis of $V$, there exists $a_1,...,a_n$ such that $v=a_1v_+...+a_nv_n$.
We define $Tv=T(a_1v_1+...a_nv_n) = a_1w_1+...+a_nw_n$

Let's make an example parallel to the proof.
$T: P_2(C) \rightarrow C^\infty$
Let's make a basis $B=(1,x,x^2)$.
Then, let $w_1=(0,1,0,1,...), w_2=(1, \frac{1}{2}, \frac{1}{3},...), w_3 = (1,1,1,...)$
Then $T_1 = w_1, Tx=w_2, Tx^2 = w_3$.
Then, $(Tp)(x) = a_1w_1 + a_2w_2 + a_3w_3$
$T(...)$
AHHHH I LOST IT!!!

Back to the proof.
Also, $T(v_1) = T(v_1+0v_2+0v_3) = w_1+0w_2+0w_3 = w_1$
Why is this linear?
If we have $v_a=a_1v_1+...a_nv_n$, and then for another $v_b=b_1v_1+...+b_nv_n$ 
Then do $T(v_a+v_b)$ and show it is equal to $Tv_a + Tv_b$ 

It is unique from the linear independent property of the basis. 
Every vector can be represented uniquely with the vectors of the basis.

$T=S \iff Tv = Sv \forall v \in V$

We can define the kernel for a linear mapping. 
Set of those vectors that the mapping maps to zero.
$\ker(T) = \{v \in V ~:~ Tv = \vec0\}$

For some $T_A: F^n \in F^m$
$ker(T_A) = \{v \in F^n ~:~ T_A v = 0\}$
$= \{v \in F^n ~:~ Av = \vec0\} = ker(A)$

A linear mapping from fin. dim. to fin. dim vector space has an interesting matrix... later....


$T: F^\infty \rightarrow F^\infty$  Forward Shift
$T(a_1,...) = T(0, a_1,...)$
$(a_1, a_2,...) \in ker(T) \iff T(a_1,a_2,..) = (0,a_1,a_2,...) = (0,0,...)$
Then $a_1 = 0, a_2 = 0, ... \implies ker(T) = \{\vec0\}$

$T: F^\infty \rightarrow F^\infty$  Backwards Shift
$T(a_1,...) = T(a_2,....)$
$T(a_1,a_2,...) \in ker(T) \iff T(a_1,a_2,...) = (a_2,a_3,...) = (0,0,...)$
Then $a_2=0,a_3=0$ $\implies ker(T) = span(1,0,...) = span(e^{(1)})$ 
We don't care what is $a_1$, but the rest should be zero.

Define $T: P(R) \rightarrow R$ such that $Tp = p(0)$ 
$T(a_0+a_1x+...+a_nx^n) = a_0+a_10+...+a_n0^n = a_0$
The kernel of $T = \{a_1x_1+...+a_nx^n ~:~ a_1,..,a_n \in R, ~ n \in R\}$

$ker(T)$ is a subspace of $V$.
In terms of matrix, one of the four fundamental subspaces.

We call a map $T: v \rightarrow w$ 
- Injective, one-to-one, if $Tv = Tw \implies v = w$

If $T \in L(V,W)$ is injective $\iff$ $ker(T) = \{\vec0\}$

Suppose that $ker(T) = \{0\}$.
We want to show injectivity.
Assume $Tv = Tv' \implies Tv - Tv' = \vec0$
Then, $Tv+(-1)Tv' = 0 \implies Tv + T(-v') = 0 \implies T(v-v') = 0$
By the definition of the kernel, $v-v' \in ker(T) = \{\vec0\}$ Then $v-v' = \vec0$ Then $v=v'$.

We have proved injectivity for whenever the kernel is zero.
Using homogenity and additivity...

Shift Forward is injective. Shift Back is not injective.

As we expect we can also define the range of the linear mapping.
It will be $ran(T) = \{Tv ~:~ v \in V\}$
The set of all outputs. It is also equal to the range of the corresponding matrix.
It is also a subspace.

It is surjective when $ran(T) = W$

With the Forward Shift, we have the restriction, that the first element has to be a zero no matter our input. Then, $(1,0,0...) \not \in ran(T)$. When we want to disprove surjectivity, we want to provide this example.

With the Backwards Shift, it is indeed surjective.
$T: F^\infty \rightarrow T^\infty$ 
$T(a_1,a_2,a_3...) = (a_2,a_3,a_4....)$
For any $(c_1,c_2,c_3,...) \in F^\infty$
We can find any vector in $F^\infty$, for example $T(1, c_1, c_2, c_3,...) = (c_1,c_2,c_3...)$
Then it is surjective, but not injective.

There exists a relation between the kernel and range.
We have to rewrite the rank theorem in the new language of linear mappings.

For matrices...
$A \in M_{m,n}(F)$
$n = dim(ran(A)) + dim(ker(A)) = dim(F^n)$

For linear mappings...
$T_A: F^n \rightarrow F^m$
$dim(ran(T_A)) + dim(ker(T_A)) = dim(F^n)$

Number of columns = dimension of codomain. (?)

What can be the generalization of the above formula for the arbitrary linear map $T \in L(V,W)$ ?
Guess: $dim(V) = dim(ker(T)) + dim(ran(T))$
We are in abstract vector spaces, and the dimension of the inf. dim. is not defined.
We need to assume that the dimension of $V$ is finite.
We expect the formula for finite dim. domain.
If $V$ is finite dimensional, then $ran(T)$ is also finite dimensional, so there is no restriction on $W$.

We want to prove $ran(T)$ is finite dimensional and $dim(V) = dim(ker(T)) + dim(ran(T))$
Let us assume $ker(T) \neq \{\vec0\}$ and also $ker(T)$ is a subspace of $V$ so it is fin. dim. since $V$ is fin. dim.
It has a basis, and we can expand the basis to $X = (v_1,...v_m,v_{m+1},...,v_n)$
Where the first $m$ entries are the basis of the kernel.
The rest correspond to the basis of the range.

We want to prove $ran(T) = span(Tv_{m+1}, ..., Tv_n)$
For this, prove: 
- $ran(T) \subseteq span(Tv_{m+1}, ..., Tv_n)$
- $span(Tv_{m+1}, ..., Tv_n) \subseteq ran(T)$

I: 
Let $w \in ran(T)$.
By definition, $\exists v \in V$ s.t. $w = Tv$
Since $X = (v_1,..,v_n)$ is a basis, then exists unique $a_1,..a_n \in F$ s.t. $v = a_1v_1 + ... + a_nv_n$.
So, $w = Tv = T(a_1v_1 + ... + anv_n) = a_1Tv_1 + ... + a_mTv_m + a_{m+1}Tv_{m+1} + ... a_nTv_n$
According to the kernel, all $Tv_1...Tv_m$ are equal to zero. 
$w = a_{m+1}Tv_{m+1} + ... a_nTv_n ~~~~ \in span(Tv_{m+1},...,Tv_n)$ 
Finally, $ran(T) \subseteq ~ span(Tv_{m+1},...,Tv_n)$

We extended to the basis according to theorem, that every LI list can be extended to a basis.

II:
Let $w \in span(Tv_{m+1},...,Tv_n) \implies \exists \beta_{m+1}, ..., \beta_n \in F$ s.t.
$w = \beta_{m+1}Tv_{m+1} + ... + \beta_nTv_n = T(\beta_{m+1}v_{m+1} + ... \beta_nv_n) ~~~ \in ran(T)$

We have proven $ran(T) = span(Tv_{m+1}, ..., Tv_n)$.

$P_3(C) \rightarrow C^3$ is not an injective mapping because their dimensions are not the same.
By the previous proposition it is not true.
$dim(ker(T)) = dim(V) - dim(ran(T)) > dim(V) - dim(W) > 0$ 


...

Using fundamental theorem to determine whether or not linear mappings are injective/surjective....

$T \in L(P_8(C), C^4)$ 
Range has an upper bound $4$ since $ran(T) \subseteq C^4$
Can the $dim(ker(T)) = 3$ ?
9 = $dim(ker(T)) + dim(ran(T))$
$9-3=7 \neq dim(ran(T))$
Therefore this cannot exist.

$T \in L(P_2(C)), C^\infty)$
$ran(T)$ is unbounded, but $ker(T)$ is bounded, so it cannot be, for example, 4.
It is a subspace of f. dim. vector space.
