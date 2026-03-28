For all linear maps, $T:V \rightarrow W$, every $Tv$ lives in $W$, and essentially, $ran(T)$ is subspace of $W$. Interesting things happen when we fix a basis.

We want to construct a map $T:P_3(R) \rightarrow F^\Omega$.
Say it is a linear map, and also that it is injective.
$\iff$ Construct a linear map, in such a way that the kernel is zero.

For this, we can take the standard basis of $P_3(R)$, being $1, x, x^2, x^3$ and map it to $(1,0,...), (0,1,0,...), (0,0,1,0,...), (0,0,0,1,0,...)$ respectively.

We want to prove that it is linear and that the kernel is zero.
...Mapping a basis to an LI list is linear and injective (Theorem).

If something is the case in $R^3$ and you use it in $P_2$, you must mention that this is implied through isomorphism. In general, $R^n, P_{n-1}$ are isomorphic.

To prove a surjective/injective mapping cannot exist, invoke fundamental theorem.

Fun fact, limits are linear maps. Surjective, but not injective.

...

Turns out, we cannot really represent infinite dimensional linear maps as matrices. However, we can represent fin. dim. linear maps as matrices. This is because these vector spaces are isomorphic to coordinate vector spaces $F^\Omega$.
Meaning we can represent this as a $M_{m,n}$ matrix.

Given $T: V \rightarrow W$. $dim(V)=n, dim(W)=m$
Then, we know that $V \cong F^n, W \cong F^m$
Then we can look at the matrix representation between these two spaces.
How do we construct it?

$V$ admits a basis, $v_1,...,v_n$ .
We can then consider a similar thing for $W$.
$W$ admits a basis, $w_1, ...,w_n$
We can to take $V$'s basis to $F^n$, so we can construct a basis.
We map it to the standard basis of $F^n$. $v_1 \rightarrow e_1, ..., v_n \rightarrow e_n$.
We use the isomorphism. 

...

Consider map $T: R^3 \rightarrow P_1(R)$
Define it as $T(\begin{bmatrix}a_1 \\ a_2 \\ a_3 \end{bmatrix}) = a_1 + a_2x$
Fix a basis for $R^3$. A good basis is the standard basis. 
$\begin{bmatrix}1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix}0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix}0 \\ 0 \\ 1 \end{bmatrix}$
 $1$      $x$     $0$ 
Then, we map every one of them to $1, x, 0$ respectively.

What will this matrix look like? We know the dimension of $R^3$ is 3, and the dimension of $P_1(R)$ is $2$, so it will be a $2 \times 3$ matrix.
Let's fill the columns.
$\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix}$
This is based on our mapping above...
It maps them entry-wise.

We can see this by matrix multiplication.
$\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix} \begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix} = \begin{bmatrix} a_1 \\ a_2\end{bmatrix} \cong a_1 + a_2x$

A question arises. It is an isomorphism with respect to our basis.
How do we know it's okay that the isomorphism in the image is this $a_1 + a_2x$?
Why not $a_2+a_1x$?
Because these isomorphisms should be invertible.

...

"Fix a basis, apply $T$ to all the vectors in the basis, then because it's linear, multiply by an arbitrary scalar." Christian, what?

...

/*
$B=(v_1,v_2,v_3)$ is a basis for $V$
$Tv_1=3v_1$
$Tv_2=-v_2$
$Tv_3=v_1-v_3$

$y_1=v_2+v_3$
$y_2=v_1+v_2$
$y_3=-v_1+v_2$
Show $y=(y_1,y_2,y_3)$ is a basis.
\*/

$\mathcal E$ is standard basis for $M_2(Z_5)$
$B=(B_1,B_2,B_3,B_4)$
Where:
- $B_1=\mathcal{E}_11$
- $B_2 = \mathcal{E}_{11}+\mathcal{E}_{12}$
- $B_3=\mathcal{E}_{11}+\mathcal{E}_{21}$
- $B_4 = \mathcal{E}_{11} + \mathcal{E}_{22}$ 
Show $B$ is a basis.
Basis $\iff$ LI and spanning
Length 4 $\iff$ prove one.

We are using isomorphism $M_2 \cong Z^4$
$[B]_{\mathcal E} = (\begin{bmatrix} 1 \\ 0 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix}1 \\ 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix}1 \\ 0 \\ 1 \\ 0\end{bmatrix}, \begin{bmatrix}1 \\ 0 \\ 0 \\ 1 \end{bmatrix})$   
We prove it the same way we did in LA1.
Since this is an isomorphic mapping, $[B]_{\mathcal E}$ is LI $\implies B$ is LI.
Corresponding SLE in matrix is ... (matrix whose columns constructed from vectors).
It is already REF. Every column has a pivot thus the solution is unique, hence $[B]_{\mathcal E}$ is LI.
Therefore, $B$ is LI.
$B$ has length $4$, and every LI list of length $4$ is a basis.

// This is $[I]_{\mathcal E \leftarrow B}$

Everything here is a composition of linear maps and changes of bases.

$[T]_{\mathcal E \leftarrow \mathcal E} = [T]_{\mathcal E \leftarrow B} [I]_{B \leftarrow \mathcal E}$ 
We do this since we are given $Tv_i=...$  UUUUGGGGGGGHHHHH
A lot of composition. Plug in numbers using isomorphism. Then inverse the change of basis matrix $[I]$. Then compose. Multiply the matrices.

Compute $T\begin{bmatrix} a & b \\ c & d \end{bmatrix}$ .
$=[T]_{\mathcal E \leftarrow \mathcal E} \begin{bmatrix} a & b \\ c & d \end{bmatrix}_{\mathcal E}=[T]_{\mathcal E \leftarrow \mathcal E} \begin{bmatrix} a & b \\ c & d \end{bmatrix}$
...
$\begin{bmatrix} 0 & 2b+2c \\ b+d & a+4b+2c\end{bmatrix}$
