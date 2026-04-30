
**Normal**: $<\cdot>: V \to R$
Axioms:
- Definiteness: $(\forall v \in V) ~~||v|| = 0 \implies v = \vec0$
- Positivity: $(\forall v \in V) ||v|| \geq 0$
- Triangle Inequality: $(\forall u,v \in V) ||u+v|| \leq ||u|| + ||v||$
- Homogeneity: $(\forall v \in V, c \in F) ||cv|| = |c| ||v||$

**Inner Product**: $<\cdot, \cdot>: V \times V \to R$
Axioms:
- Definiteness: $(\forall u \in V) <u,u> = 0 \implies u = \vec0$
- Positivity: $(\forall v, u \in V) <v,u> \geq 0 \in R$
- Linearity in first slot: $(\forall v,u,w \in V, c \in F) <cv+u,w> = c<v,w>+<u,w>$
- Conjugate Symmetry: $(\forall v,w \in V) <v,w> = \overline{<w,v>}$

We have: $||v|| = \sqrt{<v,v>}$

Inner Product induces Norm.
Norm Space is subset of Vector Space.
Inner Product Space is subset of Norm Space.

Read about parallelogram inequality.


List of vector is orthogonal $\iff$ vectors are pairwise orthogonal.
Two vectors are orthogonal $\iff v \neq w \implies <v,w> = 0 \equiv v \bot w$ 

List of vectors is orthonormal $\iff$ list is orthogonal, and also $||v_i||=1$

ON implies OG.
ON implies LI, OG does not imply LI.

**Different kinds of norms**
Frobenius norm, $$||v|| = \sqrt{<v,v>}$$ With matrices,  $= \sqrt{tr(A*A)}$

P norm:
$$||v||_p = \sqrt[p]{\sum_{k=1}^n |v_k|^p}$$
Max norm:
$$||v||_{max} = max_{i \leq n} \{|v_i|\}$$


Only the Frobenius norm and P-2 norm satisfy $||v|| = \sqrt{<v,v>}$

**For solving Gram-Schmidt**
Do not put the scalar inside the matrix, keep it out for simplicity.
First step: $e_1=\frac{v_1}{||v_1||}$
Inductive step: $e_k = v_k - \sum_{i=1}^{k-1} <v_k, e_i>e_i$


**Sample Shenanigans**

The inner product for polynomials.
$<p,q>=\int_0^1 p(x)q(x) dx = \int_0^1 (\sum_i^n p_ix^i) (\sum_i^m q_ix^i) dx$ 

To find ON basis w.r.t. $<\cdot, \cdot>$ choose any basis, preferably standard basis, and apply Gram-Schmidt.

The norm, naturally, will be the square root of the integral.

When solving for a vector w.r.t orthonormal basis, no need to solve SLE. Rather, the coordinates of $y(x)$ w.r.t $F=(e_1,e_2,e_3)$ will be $\begin{bmatrix} <y,e_1> \\ <y,e_2> \\ <y,e_3> \end{bmatrix}$

**Household Reflection**

Given an orthonormal basis $(e_1,...,e_m)$
Projection is: $$P_u(x) = \sum_{i=1}^m <x,e_i>e_i$$
The reflection lets us calculate things without calculating them.


$u$ - the vector with respect to which we are reflecting. Basically a line.
Formula for reflection: $$R_u = I-2\frac{uu^*}{||u^2||}$$
This matrix is unitary actually.

Let $x,y \in R^3$.
Their norm must be the same. Their inner product must be real.
There exists a householder reflection which sends $x \to y \iff$ 
We need to find a plane of reflection.
To find it, we have to find the vector in-between $x,y$.
We get that by calculating the average.
$n=\frac{1}{2}(x+y)$
Now we need to solve for $<c_1x + c_2y, \frac{1}{2}(x+y)> = 0$
Then we achieve vector composed of the scalars, that is our reflection vector.

Then, $H=I-2\frac{rr*}{r*r}$ 


**QR Decomposition**

Given $A \in M_{m,n}(C)$ with LI column vectors.
Then, $A=QR$, where $Q$ is the matrix whose columns consist of orthonormal list of vectors from $A$'s columns, through Gram-Schmidt. $Q$ is unitary. Every orthonormal is unitary.
Then, $R=Q^{-1}A = Q^TA$
