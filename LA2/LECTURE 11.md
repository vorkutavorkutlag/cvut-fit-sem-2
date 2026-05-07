
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

Compute a spectral decomposition for $A^*A$

We need to start similar to obtaining diagonalizability.
First step, is to compute spectrum - the set of eigenvalues of $A^*A$.
Find roots of the characteristic polynomial of $A^*A$
For convenience, we write $B=A^*A$
Find eigenvalues s.t. $P_B(\lambda) = det(B-\lambda I) = 0$
Solve for lambda in $\det(\begin{bmatrix}11 & 8 & 5 \\ 8 & 8 & 8 \\ 5 & 8 & 11\end{bmatrix} - \begin{bmatrix}\lambda & 0 & 0 \\ 0 & \lambda & 0 \\ 0 & 0 & \lambda\end{bmatrix}) = 0$
We simplify with row-column operations and cofactor expansion.
We get characteristic polynomial: $(6-\lambda)(\lambda^2-24\lambda)$
We obtain to $\sigma = \{24, 6, 0\}$
The zero is okay as long as we don't get negative (some other proof...)

$Bv=\lambda v$ 
$\lambda <v,v> = <\lambda v,v> = <B^*Bv, v> = <Bv, Bv>$
So then we get $\lambda = \frac{<Bv, Bv>}{<v,v>}$

Find an orthonormal basis of every eigenspace.
For this, we first obtain a basis of each eigenspace, then apply G-sch.
As a reminder, we do it by taking the kernel of each matrix with respect to the eigenspace; $\ker(A - I \lambda)$
Then, finding it, we apply G-sch, get orthonormal.

Finally, combine them all into one big $U$.
Finally, $B=UDU^*$

We knew how to do it for diagonalizable, and now the only difference is we apply G-sch. This $U$ is orthonormal because it is composed of orthonormal vectors, that is the importance of the theorem - the bigger basis is orthonormal.
In LA1, the point was $A$ is diagonalizable, and if we put them all in a basis they will LI.

Does G-sch guarantee the list of eigenvalues will remain "eigen"?
Important lemma states:
Let $A$ be a normal matrix and let $v,w$ be eigenvectors of $A$ corresponding to different eigenvalues of $A$. Then $v,w$ are orthonormal vectors, i.e. $<v,w>=0$

...

...

...


**Singular-Value-Decomposition** (**SVD**) for matrices.

For any matrix, not necessary to be square, not any conditions, we can find unitary matrix $U$, another unitary matrix $V$, and diagonal matrix $\Sigma \in M_{m,n}(F)$  with non-negative entries:$$A=U\Sigma V^*$$
We need to sacrifice something. See, now we have two unitary matrices.
The point is, the non-zero entries of the sigma are called singular values of $A$, positive square roots of eigenvalues of $AA*$.
The columns of $V$ are eigenvectors of $A^*A$.
The columns of $U$ are eigenvectors of $AA^*$.
Theory behind this is mostly skipped, might fill later.

How to obtain SVD for a matrix?
Let $A \in M_{m,n}(C)$, $U \in M_{m}(C)$, $\Sigma \in M_{m,n}(C)$, $V \in M_{n}(C)$
Diagonal but non-square? Don't worry. $\Sigma_{ij} = 0 \iff i \neq j$
Given $A=U \Sigma V^*$, take adjoined, $A^*=V \Sigma^* U^*$
Then we see $A^*A=V\Sigma^*\Sigma V^*$ 
Note that $\Sigma^*\Sigma$ is a $n \times n$ diagonal matrix.

We find spectral decomposition of $A^*A = VDV^*$, that's how we get $V$.
Then, we know that $D_{ii} = \lambda_i$ then $\Sigma_{ii}=\sqrt{\lambda_i}$ 

Then she does some long work for $U$, but I think we can define $U=AV\Sigma^{-1}$
She wrote, essentially, $U_i=\frac{1}{\sigma_i}AV_i$

If $\sigma_i$ is zero then we need to extend to ON. Usually, we should use G-sch, but it's okay if we don't. It's enough to just find a vector that is orthonormal to the two of them.
Then we get ON list of length $n$. Since $ON \implies LI$, and $LI$ of length $n$ is a basis, we will have achieved a basis.

