
**Singular-Value-Decomposition** (**SVD**) for matrices.
We talked about diagonalizability of matrices, and also about normal matrices.
We should reach SVD. There are more theorems for the proof, but we don't need to.

Let's go mainly to SVD, skip proof, and focus on computations and applications.
If we have time next week we will fill in the gaps. (e.g. LU decomposition)

We know about diagonalizable matrices.
$A = SDS^{-1}$ where $D$ is diagonal.
$A$ should be a square matrix, and we had necessary and sufficient conditions.
It was that $C^n$ admits a basis of eigenvectors of $A$.
Equivalently, $(\forall \lambda \in \sigma(A))\mu_a(\lambda) = \mu_g(\lambda)$ 
We obtain the eigen space, get the eigenbases, put them into one list, and that's $S$.
$D$ is diagonal whose entries are the eigenvalues repeating however many times the algebraic multiplicity is.

$S$ is invertible.
Subclass of invertible matrices is unitary. (All unitaries are square)
Definition was that $UU^* = I$. Implying $U^*U = I$
Another theorem is $U$ is unitary $\iff$ columns form ON basis of $C^n$.
If $U$ is unitary, then $U^*$ is unitary too, so then the rows would also form ON basis.
Though, should specify the columns of the adjoined instead of the rows.

We want $S$ to be unitary in $SDS^{-1}$
For this, we introduce a class of **normal matrices**; $A^*A = AA^*$

Any self-adjoined (Hermitian) matrix is normal.
Every unitary matrix is normal.
For every matrix $B, ~~ (BB*)$ is a normal matrix

**Spectral Decomposition**: square matrix $A$ is normal $\iff$ there exists a unitary matrix such that $U^*AU = D$ is diagonal.
If $D=diag(\lambda_1,...,\lambda_n)$ and $U=[U_1,...,U_n]$ then $(\lambda_i, U_i)$ where $i=1,...,n$ are orthonormal eigenpairs of $A$. Note that the $D$ has repeating eigenvalues. Note also $<U_i, U_j> = 1, 0$ depending on $i=j$.

Let $A = \begin{bmatrix}1 & 2 & 3 \\ -1 & 0 & 1 \\ 3 & 2 & 1\end{bmatrix}$ 
Obtain $U$ and $D$ s.t. $A^* A = UDU^*$
// $A$ is not normal, but $A^*A$ is self-adjoined, so it is normal.

