Last week we discussed **normed spaces**, **inner product spaces**.
Examples include $R^n / C^n$ 
All of them are vector spaces
aces but with an extra structure, this being a norm.
Then we have functions $V \to [0, \infty)$ with specific properties.

We can define norm one, norm max, norm p between two infinities.
We can also define norm on $P(C)$ later.

$||A||= \sqrt{tr(A^*A)}$ 

For inner product spaces we have a vector space, and a map $<\cdot, \cdot>: V \times V \to F$
We have properties here.

Dot product was $v \cdot w = w^*v$
Where $w^*$ is the matrix transpose of the vector with all of its entries conjugated.

We have properties of trace also: $tr(A+B)=tr(A)+tr(B), ~tr(cA)=ctr(A), ~tr(AB)=tr(BA)$
Additionally, $tr(A^*) = \overline{tr(A)}$

...

Relations between inner product spaces, traces and norms.
Every inner product space is a norm space.
Norm defined by help of inner product, $||v|| := \sqrt{<v,v>}$
Also for $p=2$ (?)

Not all norms are coming from inner products.
Norm max, norm one, cannot be induced by any inner product.

Parallelogram equality.
Let $(V, <\cdot, \cdot>)$ be an inner product space and denote the norm induced by the inner product by $|| \cdot ||$ SHE SKIPPED THE REST.

Okay. Calm down This is just a puzzle. That I can solve.

We define:
$||A||_{max} := max|a_{ij}|$
$||A||_1 = \sum |a_{ij}|$
They are not induced by any inner product space.

Ex. Show that $||\cdot||_1$ and $||\cdot||_{max}$ define norms on $M,n(C)$.

The definition of a norm is a map from $V \to R$ such that it is always $\geq 0$, zero only if vector is zero. homogeneity with absolute value scalar and we have triangle inequality.
$||v+w|| \leq ||v|| + ||w||$.

Then the inner product definition is also important for this.
Positivity, definiteness $(0 \iff 0)$, additivity in first slot, homogeneity in first slot, triangle inequality.

...

Every inner product induces norm but the converse is not true.
If parallelogram relation does not hold, then it is not induced by any inner product.
Need to find matrices that do not satisfy that relation.

Two vectors are orthogonal if their dot product is zero.

From now we combine computations and theory.
We need to keep in our mind that inner product spaces induce a norm by $||v|| := \sqrt{<v,v>}$ and we also have other definitions for previous things $v \cdot w = w^*v$.

The motivations are coming form $R^2, R^3$. Then to generalize orthogonality, we define inner product, and we try to emplace it onto other more general spaces.
In $R^2$, we have two vectors, they are orthogonal if they have a $\pi/2$ angle between them. We see also that their dot product results in a zero. 
In particular, $\cos(\theta) = \frac{v \cdot w}{||v|| ||w||}$ is the angle between them.

Dot product is now inner product. Now orthogonality in general space may be defined as when the inner product is zero.


The definition in an inner product space we say that $v,w$ are orthogonal $\iff <v,w> = 0 \iff <w,v> = 0$

Note that for that we **cannot** use the trace definition in this general, as this could be infinite dimensional, polynomial, etc. The property in definition is $<v,w> = \overline{<w,v>}$.

Consider $M_2(C), <\cdot, \cdot>_F$
Then we can prove $\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \bot \begin{bmatrix} 0 & 1 \\ 0 & 0 \end{bmatrix}$ by showing $<\begin{bmatrix} 1 & 0 \\ 0 & 0 \end{bmatrix}, \begin{bmatrix} 0 & 1 \\ 0 & 0 \end{bmatrix}> = tr(\begin{bmatrix} 0 & 0 \\ 1 & 0\end{bmatrix} \begin{bmatrix} 1 & 0 \\ 0 & 0\end{bmatrix}) = tr(\begin{bmatrix} 0 & 0 \\ 1 & 0\end{bmatrix}) = 0 \implies$ they are orthogonal.
Note that here we **can** use the trace property as it is a particular vector space that supports that definition, a coordinate space to be exact. Though, with polynomials, we would need to use integral.
We will receive formula to show that polynomials are orthogonal.

Orthogonality is very useful for us. When we have inner product space, we can discuss orthogonality. Think about it in a very abstract way.

A list of the vectors in an inner product space is called orthogonal if the vectors in it are pairwise orthogonal.
As in, every vector is orthogonal with every other vector in the list.

To recap, an inner product space is simply a vector space paired with a well-defined inner product operator.

For example, in $R^3$ the standard basis is orthogonal. It's like the edge of a cube. Every edge forms $90^o$ with the other edge, $\frac{\pi}{2}$, it is orthogonal.

A list of vectors in inner product space is called orthonormal if:
- the list is orthogonal
- the norm of each vector is one.
Latter condition equivalent to $<v_i, v_i>=||v_i||^2=1$

It is useful to have orthogonal and orthonormal lists.

Proposition states.
Let $(v_1,...,v_n)$ be orthogonal list in $(V, <\cdot, \cdot>)$ then: $$||c_1v_1+...+c_nv_n||^2 = |c_1|^2||v_1||^2+..+|c_n|^2||v_n||^2$$
for any scalars $c_1,...,c_n$.

Every orthonormal list of vectors is linearly independent.
Is every orthogonal list linearly independent?
No, because of the zero vector. Tragic!
$(0,e_1,e_2)$ is orthogonal but not LI.

$c_1v_1+c_2v_2+c_3v_3 = 0$ then  $c_1=c_2=c_3 = 0$
$\implies ||c_1v_1+c_2v_2+c_3v_3|| = 0$ definiteness of norm 
$\implies |c_1|^2+|c_2|^2+|c_3|^2 = 0$ 
$\implies c_1=c_2=c_3$

We can say orthogonal list is LI if none of the vectors are zero.
Try proving it in a similar way as above.

...

$||c_1v_1+c_2v_2||^2=<c_1v_1+c_2v_2, c_1v_1+c_2v_2> =$ Additivity, Homogeneity,
$=c_1<v_1, c_1v_1+c_2v_2> + c_2<v_2, c_1v_1+c_2v_2>$
$=c_1\overline c_1 <v_1,v_1> + c_1 \overline c_2 <v_1,v_2> + c_2 \overline c_1 <v_2, v_1> + c_2 \overline c_2 <v_2, v_2>$
$=|c_1|^2 ||v_1||^2 + |c_2|^2 ||v_2||^2$ 

In some other cases we have additivity in first slot, but we have to take conjugate out instead of just the scalar in homogeneity. 

In an inner product space, $<v, \alpha w + w'> = \overline\alpha<v, w> + <v, w'>$ 
That is because we take the conjugacy symmetry. That enables us to take it out, but at the cost of conjugacy.

It is a powerful tool to have that orthonormal are LI.

...

An orthonormal basis of $V$ is an orthonormal list of vectors in an inner product space $V$ which is also a basis. Orthonormal is already LI, so now we jut want to show spanning.
We want to show now why orthonormal basis behave much nicer than other bases.
Every LI list of the length of the dimension is basis, by previous theorems. Same goes for orthonormal bases.

Standard basis is an orthonormal basis in $C^n, R^n$.
$\mathcal E = (E_{11}, E_{12}, E_{21}, E_{22})$
is an orthonormal basis in $(M_2(C), <\cdot, \cdot>_F)$

$<E_{11}, E_{11}>_F = tr(E_{11}^* E_{11}) = tr(\begin{bmatrix} 1 & 0 \\ 0 & 0\end{bmatrix} \begin{bmatrix} 1 & 0 \\ 0 & 0\end{bmatrix}) = tr(\begin{bmatrix}1 & 0 \\ 0 & 0\end{bmatrix}) = 1$
Same with $<E_{11}, E_{12}>_F$ however it will result in zero, meaning it's orthogonal.

Advantages of orthonormal basis.
Suppose that $\mathcal B=(e_1,...,e_n)$ is an orthonormal basis of inner product space $V$.
If it is a basis, then for every $v \in V$, there exists $c_1,...,c_n$ s.t. $c_1e_1+...+c_ne_n$.
// To compute coordinates w.r.t basis, $c_1,...,c_n$, solve SLE $Ax=v$. 
Now, when we have orthonormal, we do not need to solve SLE!
Our claim is that $v$ is written as $<v, e_1>e_1 + ... + <v, e_n> e_n$
And these will be our $c_1,...,c_n$.
Instead of computing SLE, we just need to solve these inner products.
This LC is unique also since orthonormal is LI.
Then, the normal would also be the sum of those squares.
Finally, this theorem states:
$v = <v, e_1>e_1 + ... + <v, e_n> e_n$ and $||v||^2 = |v,e_1|^2 + ... + |v,e_n|^2$

This holds for every basis, not standard one.

We prove this by properties of inner product, add + homo.
 If we need, also use conjugate symmetry.

...

Remark, that the coordinate of $v$ w.r.t. orthonormal basis is $$\begin{bmatrix}<v, e_1> \\ <v, e_2> \\ ... \\ <v, e_n>\end{bmatrix}$$

Orthonormal bases are wonderful. But how do we obtain them?

#### Gram-Schmidt process
If $\mathcal B$ is an LI list, we apply **G-sch** and obtain orthonormal list $\mathcal E$ s.t. $span(\mathcal B) = span(\mathcal E)$ 
Likewise, we get basis, apply G-sch, and obtain orthonormal basis.

...

Later we do matrix factorization using this.

...

We want to talk about how we can convert
LI list to orthonormal list without changing spans.
Want to do some computations too. Maybe do some optimization problems today.

The proof for **gsch** is important. 
We construct $e_1=\frac{v_1}{||v_1||}$.
We will choose $e_1,...,e_m$ inductively as follows. 
Then construct $e_2'=v_2-<v_2,e_1>e_1$ 
And similarly $e_2=\frac{e_2'}{||e_2'||}$ 
We continue this process for all the vectors.
Finally, we achieve the orthonormal list.

The inductive formula: $$e_n' = v_n - \sum_{i=1}^{n-1} <v_n,e_i>e_i$$

...

Example.
Find an orthonormal basis of plane $S= \{(x,y,z) \in R^3 ~|~ x-y-2z=0\}$
We consider the dot product on $R^3$.

$(x,y,z)=(y+2z,y,z)=y(1,1,0)+z(2,0,1) \implies span((1,1,0), (2,0,1))$ .

Then we apply gsch to this basis.
$e_1=\frac{v_1}{||v_1||} = \frac{v_1}{\sqrt{v_1v_1}} = \frac{1}{\sqrt{5}} \begin{bmatrix}2 \\ 0 \\ 1\end{bmatrix}$ 
$e_2' = v_2 - <v_2,e_1>e_1 = \begin{bmatrix}\frac{1}{5} \\ 1 \\ \frac{2}{5} \end{bmatrix}$
Whenever achieve $e_2'$ make sure $e_1 \cdot e_2' = 0$
Then, $e_2=\frac{e_2'}{||e_2'||} = \sqrt{\frac{5}{6}} \begin{bmatrix} \frac{1}{5} \\ 1 \\ \frac{2}{5} \end{bmatrix}$ 

Now we have achieved our new orthonormal basis.
Proportions stay the same, directions stay the same, size is normalized.
Except, directions do change. We can have any basis, not just orthogonal.
gsch has the duty of making the vectors orthogonal too.

The POINT in gsch is that the span is the same. Otherwise we could just use a different basis.

Every orthogonal is LI list. Every LI list can be extended to basis. Extent to basis, apply gsch.

...

Here we need a direct sum.
Used to create inner product space and solve optimization problems.
Let $U$ be a subspace of finite dimensional inner product space $V$.
Then, $V = U \oplus U^\bot$
Where: $U^\bot = \{w \in V ~|~ (\forall u \in U) ~w \bot u \}$ 

The set of all vectors that are orthogonal to us.

Let $V$ be an inner product space. Then:
- $U^\bot$ is a subspace of $V$ for every subspace $U$ of $V$.
- $V^\bot = \{0\}$ and $\{0\}^\bot = V$ 
- If $U_1 \subset U_2$ then $U_2^\bot \subset U_1^\bot$.

We take decompose $V$ to two orthogonal subsets.
Meaning, every vector can be written uniquely as sum of vector from $U$ and $U^\bot$.

Easy to prove in coordinate space but also holds for every subspace in general $V$.
You can even be infinite dimensional. Only restriction is must be an inner product space.

Let $U$ subspace of fin. dim. dimensional space.
Need to show $V=U+U^\bot$ and $U \cap U^\bot = \{\vec0\}$.

$U$ is fin. dim. $\implies$ has orthonormal basis $\mathcal E = (e_1, ..., e_n)$.
For given vector $v \in V$, find $u \in U$ and $w \in U^\bot$ s.t. $v = u+w$.
Put $u := <v,e_1>e_1 + ... <v, e_n>e_n \in span(e_1,...,e_n) = U$.
and Let $w = v-u$.

Remains to show that $w$ is orthogonal to $u$, i.e. $w \in U^\bot$.
For this, show $<w,e_1>=...=<w,e_n>=0$
We show this by properties of inner product and our definition for $u$ and $w$.

Proof is important for computations.

...

