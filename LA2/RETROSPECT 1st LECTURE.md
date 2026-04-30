The entire lecture is about the abstraction and generalization of concepts and ideas from the previous course. We will be summarizing the concepts, definitions, proofs and intuition, as well as discussing which proofs were difficult or entertaining.

# Vector Spaces

## Definition
Let $F$ be a filed. A **vector space** over $F$ is a set $V$ equipped with two operations.
$$+: V \times V \rightarrow V$$
$$\cdot : F \times V \rightarrow V$$
Additivity and scalar multiplication respectively, such that the following holds.
$$Commutativity: (\forall u, v \in V) u+v = v+u$$
$$Associativity ~(additive): (\forall u,v \in V) u+(v+w) =(u+v)+w$$
$$Associativity ~(scalar): (\forall \alpha,\beta \in F)(\forall v \in V) (\alpha \beta)v = \alpha(\beta v)$$
$$Additive ~~Identity: (\exists!~ 0 \in V) (\forall v \in V) ~ 0 +v = v + 0 = v$$
$$Additive ~~ Inverse: (\forall v \in V)(\exists!~w \in V) ~~v+w = 0$$
$$Multiplicative ~~Identity: (\exists! ~ i \in V) ~~iv = v$$
$$Distributivity: (\forall \alpha \in F)(\forall u,v \in V)~~ \alpha \cdot(u+v) = \alpha \cdot u + \alpha \cdot v$$
$$Distributivity: (\forall \alpha, \beta \in F)(\forall v \in V)~~ (\alpha + \beta) v = \alpha v + \beta v$$

It is assumed that the reader is familiar with properties of fields.
In particular, it is crucial for every field to have attributes such as a multiplicative inverse. That is precisely why a lot of the fields we know are not suitable for vector spaces.

##### Examples

Needless to say, it is also necessary that all the results here must also be contained within the vector space. For example, $(\forall u, v \in V) ~~~u + v \in V$

$Z_{10}^5$ could not be a vector space, since $Z_{10}$ is not a field (lacks multiplicative inverse for all elements), however have dealt with vector spaces such as $Z_7^3$ in the past. Seeing as $Z_7$ is a valid field, the vector space may exist.

In this course we introduce the concept of infinite dimensional vector spaces.
The vector addition and scalar multiplication is defined as expected.

Similarly, following in the abstract fashion, we may also denote such things as: Let $X,F$ be a sets. Then $F^X$ is the set of all mappings from $X$ to $F$.
Primarily, $F^X = \{f: X \to F ~|~ f$ is a mapping $\}$.
Us, as its creators, can define addition and multiplication operations that satisfy our needs to classify that set as a vector space. If we equip it with the additive operation $(f \oplus g)(x) = f(x)+g(x)$ and multiplication operation $(\lambda f)(x) = \lambda f(x)$ we see that all the properties we desire hold.

Equivalently, the same can hold for polynomial vector spaces $P(F)$ - given the intuitive definitions, all the properties needed for vector spaces hold and we may classify them as vector spaces. It would work in the same way as we denoted the mappings, since a polynomial really is a just mapping of some sort.

#### Proposition
Let $V$ be a vector space over $F$. Then:
- $V$ has a unique additive identity.
- Every vector in $V$ has a unique additive inverse.
- For every $v \in V, 0 \cdot v = 0$
- For every $\alpha \in F, \alpha \cdot 0 = 0$
- For every $v \in V, (-1) v = -v$

###### Proofs
We may prove the uniqueness of the zero by assuming two zeros and using their property; $0 = 0 + 0' = 0'$

// In the lecture slides, there is a mistake in this part.
We may prove the vector multiplication by zero by using additivity. $0 \cdot v = (0+0) \cdot v = 0 \cdot v + 0 \cdot v$
Then, we add the additive inverse of $0 \cdot v$ to both sides.
$\implies 0 \cdot v - 0 \cdot v = 0 \cdot v + 0 \cdot v - 0 \cdot v$
$\implies 0 = 0 \cdot v$ 

For scalar multiplication by zero:
$0 \cdot \alpha = (0+0)\cdot \alpha = 0\cdot \alpha + 0 \cdot \alpha$ 
Once more, we add the additive inverse of $0 \cdot \alpha$ to both sides.
$\implies 0 \cdot \alpha - 0 \cdot \alpha = 0 \cdot \alpha + 0 \cdot \alpha - 0 \cdot \alpha$
$\implies 0 = 0 \cdot \alpha$

Lastly, to prove the additive inverse, we use distributivity and the previous part of the proposition to achieve: $v+(-1)v = 1v + (-1)v = (1 + -1)v = 0v = v$

Note that we must be using these methods to prove the propositions, as we are dealing with especially abstract vector spaces. Treating them all as coordinate vector spaces is a flawed intuition to possess, and must be avoided, as it needn't be the case.

The abstraction is important since it helps us zoom out of the specific cases we encountered these qualities at, and help us apply them in various new situations.
Additionally, stripping away all the properties to get to the very core of the topic will lead to greater understanding of why things really are the way they are.

# Subspaces

From now on, we denoted $V$ as a vector space over $F$.
Often, we work with vector spaces that are contained in larger vector spaces, we call such vector spaces **subspaces**. 

## Definition
A subset $U$ of vector space $V$ is called **subspace** if and only if $U$ is also a vector space with the same addition and scalar multiplication of $V$.

Its definition must not be confused with the proposition which soon will be covered.

Note $\{\vec0\}$ is the smallest subspace of any $V$, and $V$ is the largest subspace of any $V$.
Empty set is not a subspace of $V$, as a vector space must contain at least one element, namely the additive identity and multiplicative identity.
In the case of the zero set, the zero is both our additive and multiplicative identity.

#### Proposition
Let $U$ be a subset of $V$. Then $U$ is a subspace of $V$ if and only if the following holds:
$$Additive ~~ Identity: ~0_V \in U$$
$$Vector ~~Addition~~Closure:u_1,u_2 \in U \implies u_1+u_2 \in U$$
$$Scalar~~Multiplication~~Closure:\alpha \in F \land u \in U \implies \alpha \cdot u \in U$$
The above three conditions are easy to check.
It is important to mention, that we do not simply "forget" about the other properties of the vector space, it's simply that they are implied through these conditions being satisfied, as well as having inherited the addition and multiplication operations from the superspace $(V)$.

A proposition for polynomials notes that:
$\deg(p+q) \leq \max(\deg(p)), \deg(q))$ and additionally $\deg(\alpha \cdot p) \leq \deg(p)$
That is because the coefficients and scalars may be tricky and make us go down a degree.

##### Examples

The set of all polynomials is a subspace of the set of all mappings from $F$ to $F$.
As to say, $P(F) \subset F^F$, where $F^F = \{f: F \to F ~|~ f$ is a mapping $\}$ 
To denote a maximum degree for a polynomial, say, maximum degree $m$, we denote vector space $P_m(F)$.

The set of invertible matrices $M_2(R)$ is not a subspace of $M_2(R)$, evident by example $\begin{bmatrix}1 & 0 \\ 0 & 1 \end{bmatrix} + \begin{bmatrix}-1 & 0 \\ 0 & -1 \end{bmatrix} = \begin{bmatrix}0 & 0 \\ 0 & 0 \end{bmatrix}$ which is not invertible and therefore it is not closed.

##### Sum of Subspaces
By definition; Let $U_1,...,U_m$ be subspaces of $V$. We define the sum $U_1+...+U_m$ to be equal to $\{u_1 + ... + u_m ~|~ u_1 \in U_1 ,..., u_m \in U_m\}$
According to theorem, this sum is the smallest subspace of $V$ containing them all.
The union of two subspaces is often not a subspace, however, the sum is.

We introduce the concept of direct sum, which will be important later in the course.
Suppose subspaces $U_1,...,U_m$ over $V$. Their sum is a direction sum if every element of the sum can be written only in one way as $u_1+...+u_m$
If it is a direction sum, we use the notation $U_1 \oplus ... \oplus U_m$.

Proposition states, that given subspace $U_1,..,U_m$ over $V$, $U_1+...+U_m$ is a direct sum if and only if the only way to write $0$ as a sum of $u_1+...+u_m$ is when $u_1=...=u_m=0$.
Let us prove it.

###### Proof
Forward direction implication:
Assume $\sum U_i$ is a direct sum. Then, there exists is a unique way to represent any vector in the sum as the sum of vectors from $U_i$. $0 \in U_i ~~(\forall i \in [1,m])$, then it is possible to write $0 = 0 + ... + 0$. Then, because there is only one unique way, we know this is the only way. Thus,  $0=\sum u_i \iff (\forall i \in [1,m]) ~~u_i = 0$

Backward direction implication: 
Assume $0=\sum u_i \iff (\forall i \in [1,m])~~ u_i = 0$.
Assume there are two ways to represent a vector; $v = \sum u_i, ~~~v = \sum w_i$ 
Then, subtract the two equations; $v-v=\sum u_i - \sum w_i$
Because $U_i$ is a subset, $u_i - w_i$ is an element.
We get then; $0 = (u_1 - w_i) + ... + (u_m - w_m)$
According to our previous implication, that is only the case when $(\forall i \in [1,m]) ~~u_i = w_i$ .
Therefore, we see that these two ways are identical.
Meaning, there exists exactly one unique way.
Thus, $\sum U_i$ is a direct sum.

With implication in both sides, we have proven the proposition entirely.



Corollary states, given $U,W$ subspaces over $V$, then $V=U \oplus W \iff V = U+W \land U \cap W = \{\vec0\}$
###### Proof
We will be using previous proposition which states, that given subspaces $U_1,...,U_m$ over $V$, $\sum_{i=1}^mU_i$ is a direct sum if and only if the only way to write $0$ as a sum of $u_1+...+u_m$ is when $u_1=...=u_m=0$.

Forward implication:
Assume $V=U \oplus W$.
Prove $V=U+W$ and $U \cap W = \{\vec0\}$.

According to implication hypothesis, $V=U+W$ and $U, W$ create a direct sum.
Therefore, $V=U+W$ always holds by hypothesis.

For sake of contradiction, let there be a non-zero vector $v$ in $U \cap W$.
Then, by properties of vector space, $-v$ will also be in the $U \cap W$.
Then, by definition of additive inverse, $v + (-v) = \vec0$
However, by previous theorem, the direct sum is logically equivalent with the idea of zero can only be represented as the sum of zero vectors. 
Then again, we defined $v$ as non-zero, so we have reached an absurdity.
$\textreferencemark$ by contradiction, if $U+W$ is direct sum, $U \cap W = \{\vec0\}$

Backward implication:
Assume $V=U+W$ and $U \cap W = \{\vec0\}$
Prove $V = U \oplus W$.

According to implication hypothesis, $V=U+W$ holds, so we only need to prove $U,W$ create a direct sum. By our previous theorem, that is logically equivalent with proving that there is only one way to represent $0$ as a sum of vectors from $U, W$.

let $(v_U \in U)(v_W \in W)~v_U + v_W = \vec0$. Then, $v_W$ is the additive inverse of $v_U$. By properties of vector space, $v_U$ must also be in $W$. Then, zero must be written as a sum of a vector and additive inverse that exists both in $U, W$. The only vector that satisfies that, and its additive inverse too, is $\vec0$.
Therefore, by direct proof, if $U \cap W = \{\vec0\}$ then $U,W$ create direct sum. 


With both sides of implication, we show $V=U \oplus W \iff V = U+W \land U \cap W = \{\vec0\}$



# Back to Vector Spaces

### Linear Combinations, Span, Linear Independence...

A list of length $n$ is the ordered $n$-tuple of separated elements.
All lists are finite as $n \in N$.

#### Definition
**Linear combination** of list $v_1,...,v_n \in V$ is of form: $\alpha_1v_1+...+\alpha_nv_n$ where $\alpha_1,...,\alpha_n \in F$.

The set of all linear combinations of a list of vectors is called the **span** of the list, denoted by $span(v_1,...,v_n) = \{\sum_{=1}^n \alpha_iv_i ~|~ \alpha_1,...,\alpha_n \in F\}$.

A vector space is called **finite dimensional** if there is a list of vectors in $V$ whose span is the entirety of $V$.

A vector space is called **infinite dimensional** if and only if it is not finite dimensional.

<small> For example, </small>$P(C)$ <small>is infinite dimensional, because for every list of polynomials, there is a polynomial with a max degree. We may find any other polynomial in </small>$P(C)$ <small>with a higher degree, which would not be spanned by the list. </small>

A list of vectors $(v_1,...,v_n) \in V$ over $F$ is called **linearly Independent** if and only if the only choice of $\alpha_1,...,\alpha_n \in F$ s.t. $\alpha_1v_1 + ... + \alpha_nv_n = \vec0$ is when $\alpha_1=...=\alpha_n=0$
So, a list of vectors is LI if and only if the only way a LC of those vectors is equal to zero is if all scalars are equal to zero.

A list of vectors $(v_1,...,v_n) \in V$ over $F$ is called **linearly dependent** if and only if it is not LI.
x
<small>If we remove any vector from an LI list, it will remain LI, since the condition of the definition is satisfied (zero-scalars).
If we add a vector to an LI list, it may become LD.
If we remove all vectors which are linear combinations of other vectors, we will have made the list LI. </small>

###### Theorem
Linear Dependence Lemma.
Let $(v_1, ..., v_m)$ be a LD list in $V$, and $v_1 \neq 0$. Then exists $j \in [2, ..., m]$ s.t.:
- $v_j \in span(v_1,...,v_{j-1})$
- $span(v_1,...,v_m) = span(v_1,...,v_{j-1}, v_{j+1}, ..., v_m)$
Should know proof for it.

###### Corollary
Let $(v_1,...,v_m)$ be an LI list in $V$, and $v \in V$. If $v \not \in span(v_1,...,v_m)$, then $(v,v_1,...,v_m)$ is LI.

###### Theorem
In finite dimensional vector space, the length of every linear independent list of vectors is less than or equal to the length of every spanning list of vectors.

###### Corollary
Let $V$ be vector space such that for every positive integer $m$ there exists a linearly independent list of vectors of length $m$. Then $V$ is infinite dimensional.

We define basis-like vector $e^{(k)} = (0,...,0,1,0,...)$
An infinite series of zeros, except the $k$-th element, which is $1$.

## Bases

By definition, a basis of $V$ is a list of vectors in $V$ s.t. it is linearly independent and spans $V$.

###### Proposition
Suppose $\mathcal B$ is a basis of $V$. For every $v \in V$, there is a exactly one, unique way to write $v$ as a linear combination of the vectors in $\mathcal B$.
To prove, assume there's two, then subtract the equations, and use the zero-scalar definition of linear independence.

By the proposition, if $\mathcal B = (v_1,...,v_n)$ is a basis, then any $v \in V$ may be written uniquely as $v=\alpha_1v_1+...+\alpha_nv_n$ where $\alpha_i \in F$. Then, we call $\begin{bmatrix}\alpha_1 \\ ... \\ \alpha_n \end{bmatrix} \in F$ the coordinate of $v$ with respect to $\mathcal B$, denoted then $[v]_{\mathcal B}$.
It also follows that $[v+w]_{\mathcal B} = [v]_{\mathcal B} + [w]_{\mathcal B}$, and $[cv]_{\mathcal B} = c[v]_{\mathcal B}$ For all $v,w \in V, c \in F$.

###### Theorem
Every spanning list of vectors may be reduced to a basis of the vector space.
Proof includes loop: Is it LI? It's a basis. If not? Invoke previous theorems about removing LD vectors without changing span. Repeat.

###### Theorem
Every linearly independent list in a finite-dimensional vector space can be extended to a basis of the vector space.

#### Dimension
In particular, the aim is to define the dimension such that $\dim(F^n) = n$ for any integer.

The length of any two bases in a vector space are the same.
One is spanning, other is LI, and One is LI and other is spanning, and we use the $LI \leq spanning$ inequality from a previous theorem, to prove the same length.

Then, we may define the dimension as the length of any basis in the vector space.

###### Theorem
Given fin. dim. $V$, every LI list of length $\dim(V)$ is a basis of $V$.
Given fin. dim. $V$, every spanning list of length $\dim(V)$ is a basis of $V$.

###### Corollary
For every subspace of fin. dim. vec. space $V$, with subspace $U$, it holds $\dim(U) \leq \dim(V)$

###### Proposition
Let $U$ and $W$ be subspaces of finite-dimensional vector space $V$. Then $\dim(U+W) = \dim(U) + \dim(W) - \dim(U \cap W)$
Inclusion-Exclusion to avoid counting duplicate dimensions.

###### Proposition
Let $V$ be a finite dimensional vector space. Suppose $V=\bigoplus U_i$ (direct sum).
Then, $\dim(V)=\sum_{i=1}^n \dim(U_i)$. Since, it implies the only overlap between the subspaces is the zero vector. Look at the previous direct sum proofs for more explanation.

### Infinite Bases

Given the $e^{(k)}$ definition from previously, for $F^n$, we may consider the infinite set $M=\{e^{(i)} ~|~ i \in N\}$. Then, it is linearly independent.

By definition, a subset $\mathcal B$ in vector space $V$ is called a basis of $V$ if it is LI and spans $V$.

Infinite dimensional vector spaces do not admit any finite bases,

$P(C)$ is spanned by basis subset $M$, however, $F^{\infty}$ cannot be spanned.
That is because every polynomial only uses a finite amount of LC. 
As in, every polynomial has a degree, by definition.
However, the coordinate vector space may be infinitely long, such as $[1,1,1,1,...]$.

...

// Matrix is a vector, since matrices may create vector spaces, and vectors are simply elements of a vector space.