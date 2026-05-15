Will be discussing last topic.
Then return to SVD. During tutorial we will solve many.
Then return to the previous tests.

We discussed classes of matrices.
- Self-adjoined, s.t. $A=A^*$
- Normal matrices, s.t. $AA^*=A^*A$
- Unitary matrices, s.t. $U^*U=UU^*=I$


We discussed factorization.
- QR decomposition
- Special decomposition for normal matrices
- Singular Value Decomposition (SVD)

We will now discuss **Positive (semi) definite matrices**, and **Polar decomposition**.

Suppose that $A \in M_n(F)$ is self-adjoint. Then $A$ is
- **Positive semidefinite (PSD)** if $(\forall v \in F^n)~~ v^*Av \geq 0$ 
- **Positive definite (PD)** if $(\forall v \neq \vec0 \in F^n) v^* A v > 0$

We can look at $v^*Av$ as $<Av, v>$

We can look at matrices as linear maps.
It rotates the vectors.

We have the formula, in $R^2$, $$\theta = \arccos (\frac{<Av,v>}{||Av|| ||v||})$$
The cosine of the theta must always be positive for PSD. 
That is, $0 \leq \theta < \frac{\pi}{2}$

When we want to show that a matrix is PSD, we should use the definition. Choose an arbitrary $v$ and show that the inner product is always non-negative.
Though, there we will need to use properties of complex numbers and deconstruct them into $a+bi$. So the definition isn't the easiest.

If it is PSD but we can find we can find a nonzero vector s.t. $v^*Av = \vec0$ then it is not PD.

Theorem, instead of the definition.
If $A \in M_n(F)$ is a self-adjoint matrix, the following are equivalent.
- $(i) A$ is a positive semi-definite
- $(ii)$ All eigenvalues of $A$ are non-negative
- $(iii)$ There is a matrix $B \in M_n(F)$ s.t. $A=B^*B$
- $(iv)$ There is a diagonal matrix $D \in M_n(R)$ with non-negative entries, and a unitary matrix $U \in M_n(F)$ s.t. $A = UDU^*$ (decomposition)

To proven these equivalences, we can do $i \implies ii \implies iii \implies iv \implies i$
Though, we can always shuffle it. $i \implies ii \implies iv \implies iii \implies i$

Show $i \implies ii$
Let arbitrary $\lambda \in \sigma(A)$. Then, $\exists v \neq \vec0 \in F^n$ s.t. $Av = \lambda v$
Now by PSD of $A$, we compute $0 \leq v^*Av = v^*(\lambda v) = \lambda v^* v = \lambda ||v||_2^2$
Therefore, $\lambda \geq 0$

Show $ii \implies iv$
Here, indeed, spectral decomposition.
$A$ is self adjoint by assumption, then it is normal by decomposition.
So, it has a spectral decomposition $A = UDU^*$ (spectral theorem)
We know that diagonal entries of $D$ are eigenvalues of $A$.
We assume that all of them are non-negative. Tada!

Show $iv \implies iii$
Set $B = \sqrt D U^*$
Then, we have $B^*$ to be $U \sqrt D$
Indeed, $B^*B = U \sqrt D \sqrt D U^* = UDU^*$
Therefore, we indeed have $A=B^*B$

Right now we can only define square roots of positive diagonals.
At the end of today, we want to define square roots for all PSD.
PSD are generalizations of non-negative scalars, which are secretly... $1 \times 1$ matrices.

Show $iii \implies i$
It is given that $A = B^*B$
Now, show $(\forall v \in F^n)$
$v^*B^*Bv \geq 0 \equiv (Bv)^* (Bv) \geq 0 \equiv <Bv, Bv> \geq 0 \equiv ||Bv||^2 \geq 0 \equiv \top$

Finally, we have proven they are all equivalent.

Theorem. Similar to previous, but for PD.
Let $A \in M_n(F)$ be self-adjoint. The following are equivalent:
- $A$ is positive-definite.
- All eigenvalues of $A$ are strictly positive.
- There is an invertible matrix $B \in M_n(F)$ s.t. $A=B^*B$
- There is a diagonal matrix $D \in M_n(R)$ with strictly positive entries and unitary matrix s.t. $U \in M_n(F)$ s.t. $A=UDU^*$

PSD implies that all the diagonal entries are non-negative. Says nothing about others.
If $A$ is PD, then all diagonal entries are strictly positive.

Theorem.
Suppose self-adjoint block matrix.
$A=\begin{bmatrix}A_{11} &A_{12}&...&A_{1n} \\ A_{12}^* & A_{22} & ... & A_{2n} \\ ... & ... & ... & ... \\ A_{1n}* & A_{2n}^* & ... & A_{nn}\end{bmatrix}$
Where $A_{ij}$ is not a scalar, but actually a matrix itself.
Assume this matrix is P(S)D. Then $\implies$, the diagonal blocks, $A_{11},...,A_{nn}$ are all P(S)D.
This statement is true for PSD and PD.

These blocks have no dimension restrictions. Can be non-square,

We really should have that adjointness. That "symmetry" (with conjugacy)

Sylvester's Theorem.
Let $A \in M_n(F)$ be self-adjoint. Then, $A$ is positive definite (PD) IF AND ONLY IF:
For all $1 \leq k \leq n$ the determinant of the top-left $k\times k$ block of $A$ is strictly positive. 
i.e. non-zero and non-negative.

In the exam, we will need to know all the ways to prove PD or PSD.
Equivalences, blocking, Sylvester, etc.

In the exam, we will need to prove/disprove P(S)D in several ways.
First show it is self-adjoint.
Then, check if the diagonal entries to try and disprove.
Then we check the eigenvalues are non-zero, and otherwise, block matrices.
Also could use Sylvester's theorem.
If in three ways, then we should find the matrix $B$
Also could use definition...

Theorem.
Suppose that $A,B \in M_n$ are positive (semi) definite.
$P \in M_{m,n}$ is any matrix and $c > 0$ is a real scalar. Then
- $A+B$ is positive (semi) definite.
- $cA$ is positive (semi) definite.
- $A^T$ is positive (semi) definite.
- $P^*AP$ is positive semi-definite. Furthermore, if $A$ is positive definite, then $P*AP$ is positive definite if and only if $rank(P)=m$

Principle Square Root of a Matrix.
Suppose $A \in M_n(F)$ is positive semi-definite.
There exists a unique positive semi-definite matrix $P \in M_n(F)$ s.t. $$A=P^2$$
Then, we call $P$ the square root of $A$; $\sqrt A = P$
We find $P$ by finding the spectral decomposition and setting $P = U \sqrt D U^*$

We should show in two ways that $A$ is PSD. Then obtain the square root (via spectral).

Polar decomposition.
Let $A \in M_n(F)$ Then there exists a unitary matrix $U \in M_n(F)$ and a positive semidefinite matrix $P$ s.t. $A = UP$
Furthermore, $P$ is unique and $P = \sqrt{A^*A}$

This stems from $z \in C \implies z = a+ib$ and then $\theta = \arctan(\frac{b}{a})$ and then $z=re^{i\theta}$ where $r$ is the radius, being the normal of the $z$.
Every arbitrary $z$ can be written as $re^{i\theta}$

// Ha-ha! Rei Theta

This is the polar decomposition of $z$.
We generalize this for all matrices.

This will not be in our exam.
$U$ is not unique (rank shenanigans?) but $P$ is always unique.
$U$ is found by going to the spectral decomposition, with $A^*A$, long thing...

...

The trace of matrix products is 'commutative'. $tr(AB) = tr(BA)$ since the diagonal is the same.

The Forbenious norm of $A \in M_{m,n}(F)$, if $A=U \Sigma V^*$ then by the properties of unitary matrices and the trace, $||A||_F^2 = tr(\Sigma^2) = tr(\Sigma)^2 = \sigma_1^2+...+\sigma_r^2$.
Where $\sigma_i$ are singular values of $A$.

From the linear map point of view, that norm is not good. (What?)

We define the **operator norm** of $A$ to be $||A||$ defined by $$\max\{\frac{||Av||}{||v||} ~|~ v \neq \vec0\in F^n\}$$
Which is equivalent with some other values. Look up later.

If we have the SVD, we can define:
- operator norm $||A||=\sigma_1$
- forbenious norm $||A||_F=\sqrt{\sum_i \sigma_i^2}$


Also, $||A^*A|| = ||A||^2$. This is very useful for linear mappings.
This is the basics of $C^*$ algebra.

Polar won't be in the exam, and operator norm just remember that you can define Forbenious and Operator norms via SVD.

...

There are two cases of computing SVD for $A \in M_{m,n}$
- $(I)$ If $n \leq m$; $A^*A$ has smaller size than $AA^*$, so we do spectral on $A^*A \in M_{n}$
- $(II)$ Otherwise; apply spectral decomposition on $AA^* \in M_{m}$

For $I$:
Compute spectral decomposition s.t. $A^*A=VDV^*$
We order the eigenvalues in the diagonal in a decreasing order (biggest first).
We define the singular values of $A$ to be the square roots of the $D$.
Now we want to find $A = U \Sigma V^*$
Then, to compute $\Sigma$, take the singular values of $A$.
The $V^*$ is the  same from the spectral decomposition.
Then we find $U$ by taking the the adjoint of those other matrices and isolate and compute.

Spectral decomposition is not unique.
Therefore, SVD is not unique.

For $II$:
Consider instead the spectral decomposition $AA^* = UDU^*$
The non-zero eigenvalues of $A^*A$ and $AA^*$ are same.
The rest of the steps are pretty much the same (I think)

Show that a given matrix is PD.
First, show that the matrix is equal to its adjoint.
For example, could show that all eigenvalues are strictly positive.

The determinant is the product of the eigenvalues (with respect to their algebraic multiplicity).

If $V, W$ are normed spaces, than $L(V,W)$ is also a normed space.