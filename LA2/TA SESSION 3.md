
## Isomorphism

Last time we talked about linear mappings.
A mapping between two vector spaces over the same field is linear if it satisfies homogeneity and additivity.
Homogeneity: $(\forall v \in \mathbb{V})(\forall c \in \mathbb{F})~~~ T(cv) = cTv$ 
Additivity: $(\forall v_1, v_2 \in \mathbb{V})~~~ T(v_1+v_2) = Tv_1 + Tv_2$ 

A matrix from $R^3 \rightarrow R^2$ is a linear function.
Every finite linear mapping has a corresponding matrix.
This is because of the linearity of matrices.

Linear mappings also exists in infinite dimensional vector spaces.
We have seen that through forward/backward shifts $\mathbb{F}^\infty \rightarrow \mathbb{F}^\infty$ .

All applied science nowadays is based on approximating hard things with linear maps.
Cryptography, physics, machine learning, etc.

We talked about subspaces.
$\ker(T) = \{v \in \mathbb{V} | Tv = \vec0\}$
$ran(T) = \{w \in \mathbb{W} | v \in V \land Tv = w\}$

A linear map is injective $\iff$ its kernel is zero.
A linear map is surjective $\iff$ its range is equal to its codomain.

If we have both, we are a bijective linear map.
These will be very important today.

Forward-Shift is injective. Backward-Shift is surjective.

Isomorphism.


We have to vector spaces which are not the same.
Consider, for example, $\mathbb{R}^3, \mathbb{P}_2(\mathbb{R})$
These contain $\begin{bmatrix}17 \\ 5 \\ -12\end{bmatrix}$ and $17+5x-12x^2$ respectively. 
Though, they have some similarities. We add each component to its respective corresponding component by index/entry.

Then it stands that every polynomial should be representable with a vector, and every vector should be representable with a polynomial.

An isomorphism is a structure preserving bijection. The structure includes the operations.

A map $T: \mathbb{V} \rightarrow \mathbb{W}$ is an isomorphism if:
- $T \in L(\mathbb{V},\mathbb{W})$
- $T$ is bijective.

If there exists an isomorphism between two **vector spaces**, (bijection is invertible, this is an equivalence relation), then these are isomorphic to each other.
Denoted: $\mathbb{V} \cong \mathbb{W}$

We usually want to prove bijection via injectivity and surjectivity, the former we prove usually by showing the kernel is zero.
For surjectivity, we can apply the definition of it.
For example,
Let $a_1+a_2x+a_3x^2 \in \mathbb{P}_2(\mathbb{R})$. Choose $\begin{bmatrix}a_1 \\ a_2 \\ a_3\end{bmatrix} \in \mathbb{R}^3$ .
The image of that vector is the polynomial of interest.
Since the polynomial is arbitrary, the mapping is surjective.

The algebraic properties, scalar multiplication, inverses, identities, are the same.
This is the notion of equality of a vector space.

Proposition: $\mathbb{P}_{n-1}(\mathbb{F}) \cong \mathbb{F}^n$ 


A way to disprove an isomorphism is by assuming there exists isomorphism and then deriving some absurd consequence.

If we take the example $(a,0,0,0,...)$, that subspace of $\mathbb{F}^\infty$ is isomorphic to $\mathbb{F}$.
Note, though, it is isomorphic only as a vector space. The algebraic operations are not the same as $\mathbb{F}$, as in, we cannot do addition and multiplication of vectors the same as we can of scalars. That is the important distinction to be made between being the same and being isomorphic as vector spaces.

For example for disproving isomorphism, we could use the theorem that the mapping is injective. Then, we have a theorem that is should map LI to LI. But then, it maps LI of one length to LI of another length, which may be too long, which is impossible. Absurd!


Composition of bijection mappings is bijective.
Proof of injectivity:
$x \in \ker(g \circ f) \implies f(x) \in \ker g \implies f(x) = \vec0 \iff x \in \ker(f) \iff x = \vec0 \implies \ker(g \circ f) = \{\vec0\}$ 
Proof of surjectivity:
Exercise for the reader :P

Then, isomorphism is an equivalence relation as it satisfies RE, SY, TR

The following is the big theorem in LA2.
Let $\mathbb{V}$ be a fin. dim. v.s. over $\mathbb{F}^n$, and $\dim(\mathbb{V}) = n$ ...
Then, $\mathbb{V} \cong \mathbb{F}^n$ 

Since $\mathbb{V}$ is finite dimensional, it admits a basis $X = (v_1,...,v_n)$
$\forall u \in \mathbb{V} ~:~ (c_1,...,c_n) \in \mathbb{F}^n$ is a coordinate representation w.r.t. $X$ s.t. $u=\sum_{i=1}^n c_iv_i$ 
Now let's define the isomorphic mapping.
$[\cdot]_X: \mathbb{V} \rightarrow \mathbb{F}^n$ s.t. $[u]_X ~^{def}= (c_1,...,c_n)$ 

Additivity:
$\forall u,w \in \mathbb{V}$
$[u+w]_X = [\sum_i c_i^uv_i + \sum_i c_i^w v_i]_X =$ 
$=[\sum_i (c_i^u+c_i^w)v_i]_X =$
$=(c_1^u + c_1^w, ..., c_n^u + c_n^w) = (c_1^u,...,c_n^u) + (c_1^w,...,c_n^w)$
$=[\sum_i c_i^nv_i]_X + [\sum_i c_i^w v_i] = [u]_X + [w]_X$

Homogeneity:
$\forall v \in \mathbb{V}, \forall L \in \mathbb{F}$
$[Lu]_X = [L \sum_i c_i v_i]X = [\sum_i (Lc_i) v_i)]_X = (Lc_1,..., Lc_n)$
$=L(c_1,...,c_n) = L[u]_X$

Injectivity:
$\forall x \in \mathbb{V}$ s.t. $[x]_X = \vec0 \implies (x_1,...,x_n) = (0,...,0) \implies x = \sum_i 0v_i = \vec0$
Thus we prove $\ker([.]_X) = \{\vec0\} \implies$ inj.

Surjectivity:
$\forall (y_1,...,y_n) \in \mathbb{F}^n ~:~ \exists u \in \mathbb{V}$ s.t.
For $[u]_X = (y_1,...,y_n)$ Choose $u=\sum_i y_i v_i$ 
Then we construct jut that.