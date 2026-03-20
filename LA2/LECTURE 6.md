
Consider two vector spaces of the same field, $V,W$
Then $L(V,W)$ is the set of all linear maps from $V$ to $W$.
We defined kernel, range of the map.
We discussed injectivity, surjectivity for linear maps.
Also, the fundamental theorem of linear algebra.
Need to know the proof of it.

We will do isomorphism now.
To do matrix computations, we put it all into a column vector, right?
That is the isomorphism, that we didn't have the tool of earlier.

we can say two vector spaces are the "same" as v. spaces.
"same" as in, isomorphism.

We have a proposition. If we have a linear map from $Y$ to $W$, and another linear map from $W$ to $Z$, then the composition mapping from $Y$ to $Z$ is also a linear mapping.
$T \in L(Y,W) \land S \in L(W,Z) \implies TS \in L(V,Z)$
This is a good exercise, try to prove this.

$TS(\alpha z_1 + z_2) = T(S(\alpha z_1 + z_2)) = T(\alpha Sz_1 + Sz_2) = \alpha T(Sz_1)+ T(Sz_2) = \alpha (TS)z_1 + (TS)z_2$

Using definition of composition.
Using linearity of S.
Using linearity of T.
We showed homogeneity and additivity for the composition, proving it too is linear. 

A map is called invertible if there exists a map such that the composition is the identity map of that field.
If linear mapping $T \in L(V,W)$ is inv. then $T^{-1} \in L(W,V)$

An invertible (bijectivity) linear map is an isomorphism.
We give this definition.
An invertible linear map is called ISOMORPHISM.
The philosophy for this word... Why we give it a new term? They are not only invertible, they are also linear. That gives us a lot of information.
The notion is general. 
We have a map from $V$ to $W$, linear and inv. , then these two vector spaces is isomorphism.

If there is an isomorphism from $V \rightarrow W$ then we call $V$ isomorphic to $W$.
We used notation $V \cong W$. 
Is this an equivalence relation in the set of all vector spaces over the same field?
It is reflexive, transitive, symmetric.
If we want to show isomorphism, we need to find an isomorphic mapping.
- RE: $V \cong V$ for this we use the identity mapping. Holds.
- SY: $V \cong W \implies W \cong V$ If a map is invertible, its inverse is invertible.
- TR: $V \cong W \land W \cong Z \implies V \cong Z$ We can have the composition of the mappings. We also saw in discrete math that it is invertible. 
Finally all of it holds, so the isomorphism is an equivalence relation.

$T$ is invertible $\iff$ it is surjective and injective.

Nice, useful problems.
$T: V \rightarrow W$ is injective.
Then, $T$ maps any LI sequence in $V$ to an LI sequence in $W$.
It carries LI list to LI list.
If $B=(v_1,...,v_n)$ is LI in V, then $T(v_1,...,v_n)$ is LI in W.
We want to prove this. We want to use definitions of LI.
Being, that the linear combination wherein the list is equal to zero is only possible when all the scalars are equal to zero.

Case $n=3$
$B=(v_1,v_2,v_3)$ is LI
$T$ is inj.
Want to show $T(v_1,v_2,v_3)$ is LI in W.

Show if $c_1Tv_1 + c_2Tv_2 + c_3Tv_3 = 0$ then $c_1=c_2=c_3=0$

$c_1Tv_1 + c_2Tv_2+c_3TV_3 = \vec0 \implies$ linearity of $T$.
$T(c_1v_1+c_2v_2+c_3v_3) = \vec0 \implies$ injectivity of $T$ for $\vec0$. (kernel)
$c_1v_1+c_2v_2+c_3v_3 = \vec0 \implies$ definition of linear independence.
$c_1=c_2=c_3=0$
Q.E.D for LI list B, injective T, T(B) is LI.

Note that we also use the definition of the kernel for the injectivity.
If $T$ is injective, $\ker(T) = \{\vec0\}$ therefore if $Tv = \vec0$ then $v = \vec0$

Now, naturally, now that we see $A \implies B$, we want to see if $B \implies A$.
We want to know if the converse is true.

If $T \in L(V,W)$ maps every LI sequence in $V$ to LI sequence in $W$,
then $T$ is injective.

We will use contraposition.
Assume $T$ is not injective. 
Then the kernel is not zero.
We can find a nonzero vector in kernel of T.
a nonzero vector forms an LI list.
then we map that list of a single vector. and we get a list of zero. and (0) is not LI.

...

The direct proof approach falls down for infinite dimensional vectors, as you cannot write them as a linear combination. Even if we don't use natural indices, infinite sums are not defined for the definition of linear independence.

...

If $T \in L(V,W)$ and $V, W$ are finite dimensional, if $T$ maps a spanning list of $V$ to a spanning list of $W$, then $T$ is surjective.

To show surjectivity, for every $w \in W$, need to find $v \in V$ s.t. $Tv=w$
Since $Tv_1, Tv_2, Tv_3$ spans $W$. 
$\exists c_1,c_2,c_3$ s.t. $c_1Tv_1 + c_2Tv_2 + c_3TV_3 = w$
Then we use linearity. $T(c_1v_1+c_2v_2+c_3v_3)=w$
($\forall w \in W) ~ w \in ran(T)$

Prove the converse as exercise.

...

Assume $V$ is fin. dim.
How to construct an inj. linear map from $V \rightarrow W$ ?
Fix a basis $B=(v_1,...,v_n)$ of $V$.
To construct a linear mapping from $V \rightarrow W$, 
enough to choose list $w_1,...,w_n \in W$
and define $Tv_1=w_1,...,Tv_n=w_n$
We want this to be injective.
To make it injective enough to choose LI list $w_1,...,w_n \in W$
and define $Tv_1=w_1,...,Tv_n=w_n$.

$T(v) = \vec0$
$\implies v = c_1v_1+...+c_nv_n$
$\implies Tv=c_1Tv_1+...+c_nTv_n$
$= c_1w_1+...+c_nw_n = \vec0$
// $(w_1,...,w_n)$ is LI.
$c_1=...=c_n=0 \implies v = 0 \implies \ker(T) = \{\vec0\}$
$\implies T$ inj.

...

Construct injective mapping $T: P_3(C) \rightarrow C^4$
We use (LI) basis for $P_3$; $B=(1,x,x^2,x^3)$
Then, we use the standard basis to fix LI list for $\mathbb{C}^4$ 
Then define $Tb1=w_1,Tb_2=w_2, Tb_3=w_3, Tb_4=w_4$

...

TLDR:
- Fix basis for $V$.
- choose a spanning list on $W, T$ is surj.
- choose an LI list on $W, T$ is inj.

Once we have a $T$ which is both inj. and surj. i.e. bijective, it is isomorphic.
Then we say $V \cong W$ 

###### Proposition
Let two finite dimensional vector spaces be over the same field such that their dimensions are equal. Consider the bases for them. The linear map given by $Tv_i=w_i$ (from basis to basis) is an isomorphism.

...

$T: M_2(\mathbb{Z}_5) \rightarrow \mathbb{Z}_5^4$ 
We fix the basis for the matrix, $E_{11}, E_{12}, E_{21}, E_{22}$
And fix a basis for the vector, $(e_1,e_2,e_3,e_4)$
Then, we define mapping :
$TE_{11} = e1, TE_{12} = e2, TE_{21} = e3, TE_{22} = e4$ 
Then $T$ is inj. surj. and linear. Finally it is an isomorphism.
...

Any finite dimensional vector space $V$ with dimension $n$ is isomorphic to $F^n$

...

Using isomorphism, we can morph abstract vector spaces into $F^n$, do the computations there the same as in LA1, and then go back to the abstract.

Given fin. dim. vector space over a given field, and $V \cong F^n$ via $T$
- $T$ is inj $\implies T$ maps LI to LI.
- $T^{-1}$ is inj $\implies T^{-1}$ maps LI to LI
$\implies (v_1,...,v_n)$ is LI $\iff$ $(Tv_1,...,Tv_n)$ is LI in $F^n$ 

For example, to argue whether $(x,x+1,x^2-x)$ is LI or not in $P_2(\mathbb{C})$
We can define an isomorphism to $\mathbb{C}^3$ .
Then, we solve SLE in $C^3$ after the mapping, and determine whether or not it is LI there. If it is, it is LI in the original vec. space. If it is not, it is not LI in the original vec. space.

Same idea holds for spanning. Isomorphism maps spanning to spanning.
It maps a basis of $V$ to a basis of $W$.

...

...

...

If $V$ is a fin. dim vector space over $F$ with dimension $n$,
Then $V \cong F^n$

If $V, W$ are fin. dim. and with equal dimensions, then $V \cong W$.
We can prove this by the equivalence relation of the isomorphism.
Also could do it by fixing the bases and showing inj. surj. linear map.

If $V$ is f. dim. and $V \cong W$, then $W$ is f. dim. with same dimension as $V$.
By FTLA, $ran(T)$ is fin. dim. Since $T$ is surjective, $ran(T) = W$, so $W$ is fin. dim.
By FTLA, $dim(V)=dim(ker(T)) = dim(ran(T)) \implies dim(V) = dim(W)$
// Kernel of $T$ is zero.

Now with both implications,
$$V \cong W \iff \dim(V) = \dim(W)$$

True/False?
$P_3(\mathbb{C})$ and $\mathbb{C}^3$ are isomorphic.
False, $\dim(P_3(\mathbb{C}))=4$ and $\dim(\mathbb{C}^3)=3$ which are not equal.
Therefore, they cannot be isomorphic.

However, $P_5(\mathbb{C})$ and $M_{2,3}(\mathbb{C})$ are isomorphic.

...

If $V$ is fin. dim. and $W$ is inf. dim. they cannot be isomorphic.

A subspace cannot be isomorphic to its superspace as it'd need to have the same dimension, which only happens if it's the trivial case.

What about the infinite dimensional case?
Being infinite dimensional is more wide. We can still have Isomorphism.
We can make a bijection between $(a_1, 0, a_2, 0, a_3, ....)$ to $(a_1, a_2, a_3,...)$
As in, from $F^\Omega$ and its subset $\{(a_1, 0, a_2, 0,...) ~:~ a_1,a_2, ... \in F\}$

Inside of an infinite set, we can have an infinite subset, with which there is a bijection.
Similarly, we are seeing an analogous case here.

Fin. Sets have bijection $\iff$ they have same cardinality.
There is a linear bijection (isomorphism) between two fin. dim. vectors $\iff$ they have the same dimension.

When we compared bijection from $\mathbb{N}$ to  $\mathbb{N}^2$ we dabbled in infinite sets.
Likewise, that analogy here only makes sense when we make an isomorphism between inf. dim.vector spaces.

...

...

We want to generalize Change of Basis from LA1.
We will focus on fin. dim. vector spaces.

Let $V, W$ be fin. dim. v. spaces and $T \in L(V,W)$.
Assume $B, X$ are bases for $V, W$ respectively.
Then there exists unique matrix in $M_{m,n}(F)$ denoted by $[T]_{X \leftarrow B}$ s.t. for every $v \in V$: 
$$[Tv]_X = [T]_{X \leftarrow B}[v]_B$$

We have a proposition also, $$[ST]_{X \leftarrow B} = [S]_{X \leftarrow \epsilon} [T]_{\epsilon \leftarrow B}$$
Blah blah blah need to figure out linear mapping's change of basis matrices later.

Friday 10th of April 4:15 PM - 6:15 PM first test.
Material will drop later.