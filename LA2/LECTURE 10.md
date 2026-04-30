Proof for theorem 5.2.
Let $U$ be a subspace of a finite dimensional inner product space $V$, then $V = U \oplus U^\bot$ 
Where the orthogonal complement $U^\bot = \{w \in V ~|~ w \bot u, \forall u \in U\}$
Where $w \bot u \iff <w, u> = 0$.

Exercise: $U^\bot$ is always a subspace.

Also note $U^\bot \cap U = \{\vec0\}$
Let $z \in U$, also $z \in U^\bot$.
Then since every vector in $U^\bot$ is orthogonal to every vector in $U$, $z \bot z \iff <z,z = 0> \iff z=0$ by definiteness. 

The smaller the subspace, the bigger the complement.

Anyway back to the proof.
It says we can decompose every vector space.

We need to show $V=U+U^\bot$
$U$ is a subspace of a finite dimensional $V$.
Then, $U$ is finite dimensional $\implies U$ admits basis $B=(v_1,..,v_m)$
Since we are in the inner product space we are interested in the orthonormal basis.
We apply the Gram-Schmidt process to $B$, we obtain an orthonormal basis $\mathcal E = (e_1,...,e_m)$ of $V$.

For given $v \in V$, put $u=<v,e_1>e_1+...+<v,e_m>e_M$
So, $u \in span(e_1,...,e_m) = U$

Then, let $w=v-u$.
Our claim is that $w \in U^\bot$

Since $\mathcal E$ is a basis of $U$ it is enough to show that that $w$ is orthogonal to every $(e_1,..,e_m)$
Equivalently, $<w,e_1>=...=<w,e_m>=0$
Compute for every one.
$<w,e_1>=<v-u,e_1>=<v,e_1> - <u,e_1> = 0$
Then, $v = v + (v-u) = v + w \in U + U^\bot$
Where $v$ is an arbitrary vector in the superspace.
Now, we can show that $V=U+U^\bot$
Also, we have shown that the intersection between the subspaces is always zero, so by theorem, they are a direct sum.

Q.E.D $V = U \oplus U^\bot$

We have three different types of computational problems. Vectors, Matrices, Polynomials.

...

Problem 1:
Let $U = span(\begin{bmatrix}1 \\ 1 \\ 0\\ 0\end{bmatrix}, \begin{bmatrix}1 \\ 1 \\ 1 \\ 2\end{bmatrix})$
Write $v=\begin{bmatrix}1 \\ 2 \\ 3 \\ 4\end{bmatrix}$ as a sum of $u,w$ where $u \in U, w \in U^\bot$

Step 1: Find a basis $B$ of $U$.
Step 2: Apply Gram-Schmidt to the basis, transforming it to orthonormal.
Step 3: Set $u=<v,e_1>e_1+...+<v,e_m>e_m$ then $w=v-u$

Either these vectors are a basis or not.
Step 1:
$\begin{bmatrix}1 & 1 \\ 1 & 1 \\ 0 & 1 \\ 0 & 2\end{bmatrix} \rightarrow_{GEM} \begin{bmatrix}1 & 1 \\ 0 & 0 \\ 0 & 1 \\ 0 & 0\end{bmatrix}$  
Then, $B=(v_1,v_2)$ is indeed a basis of $U$.

Step 2:
Apply G-sch process to B.
Note the inner product in $R^4$ is the dot product.
That being, $<v,w> = v \cdot w = v_1w_1+...w_nv_n=w*v$
$e_1 = \frac{v_1}{||v_1||}$ 
Then, $||v_1|| = \sqrt{<v1,v1>}= \sqrt{1^2+1^2+0^2+0^2}=\sqrt2$
Now, $e_1=\frac{1}{\sqrt2} \begin{bmatrix}1 \\ 1 \\ 0 \\ 0\end{bmatrix}$

Next, $e_2' = v_2 - <v_2, e_1>e_1 = \begin{bmatrix}1 \\ 1 \\ 1 \\ 2\end{bmatrix} - <\begin{bmatrix}1 \\ 1 \\ 1 \\ 2 \end{bmatrix}, \frac{1}{\sqrt2} \begin{bmatrix}1 \\ 1 \\ 0 \\ 0\end{bmatrix}> \frac{1}{\sqrt2} \begin{bmatrix}1 \\ 1 \\ 0 \\ 0\end{bmatrix}$

Use properties of inner product and compute.
Then, $e_2'=\begin{bmatrix} 0 \\ 0 \\ 1 \\ 2\end{bmatrix}$
Now, obtain the norm.
$||e_2||=\sqrt{<e_2,e_2>} = \sqrt 5$
$e_2 = \frac{1}{\sqrt 5}\begin{bmatrix} 0 \\ 0 \\ 1 \\ 2\end{bmatrix}$


Step 3:

$u = <v, e_1>e_1 + <v,e_2>e_2$
Compute the inner products and multiplications using the previous steps.

And then let $w = v - u$ use the formula from the previous proof to show that $w \in U^\bot$.

Finally, we will have shown $v=u+w$

...

...

...

Why do we care about this decomposition?

$V$ needn't be finite dimensional in the previous theorem, it is enough for $U$ to be finite dimensional of the inner product space $V$.

$U$ is a finite dimensional subspace of an inner product space $V$.
Then, $V = U \oplus U^\bot$

Can be written uniquely since $U, U^\bot$ are a direct sum.
Then, $v=u+w$ can be written uniquely.

We define notation $$P_U v := u$$
So, $$P_Uv = <v, e_1>e_1+...+<v,e_m>e_m$$

Then we can say $P_U : V \to V$ s.t. $$v \to <v,e_1>e_1+...+<v,e_m>e_m$$

It has a few very interesting properties.
- $P_U$ is a linear map. $P_U \in L(V)$ // through linearity in first slot.
- $ran(P_U) = U$
- $P_U u = u$ since $u=u+0$ where arbitrary $u \in U$, $0 \in U^\bot$ 
- $P_u^n v = u$ for $n \geq 2$  // definition, then composition, ^^
- $<P_uv, w> = <v, P_u w>$ // hm? Not sure, ask TA

...

Theorem states.
Suppose that $U$ is a subspace of finite dimensional inner product space $V$ and $v$ is arbitrary element $\in V$. Then $$||v - P_U v|| \leq ||v-u||$$
It is a projection of the $v$ on $U$, by mathematical language, is $P_U v$
Then, if it is a projection, it says, look at any other vector in $U$. The smallest distance is between $v, P_U v$. The rest, $v, u$ are longer.

The actually projection is $P_U(v)$. The closest vector in $U$.
Not $v- ...$ . $||v - P_U(v)||$ is the distance

...

Find the closest vector in the plane $S = x-7y+2=0$ to vector $v=\begin{bmatrix}3 \\ -2 \\ 2\end{bmatrix}$
Solution.
We need to find$P_S \begin{bmatrix}3 \\ -2 \\ 2\end{bmatrix}$ 

Need to find a formula of $P_S$.

Step 1: Find a basis $B$ of $S$.
Step 2: Apply G-sch to $B$ to obtain orthonormal basis $\mathcal E=(e_1,e_2,e_3)$ of $S$ 
Step 3: $P_S(v)=<v,e_1>e_1+<v,e_2>e_2,<v,e_3>e_3$

Step 1:
To find a basis, let's first find a spanning list for it.
$w = \begin{bmatrix}x \\ y \\ z\end{bmatrix} \in S \implies w = \begin{bmatrix}4y - z \\ y \\z \end{bmatrix} = y \begin{bmatrix}4 \\ 1 \\ 0\end{bmatrix} + z \begin{bmatrix}-1 \\ 0 \\ 1 \end{bmatrix}$ 
Therefore, $S = span(\begin{bmatrix}-1 \\ 0 \\ 1 \end{bmatrix}, \begin{bmatrix}4 \\ 1 \\ 0\end{bmatrix})$
Then, let $B=(v_1,v_2)$.
We do GEM and confirm it is LI (confirming it is a basis).
Then $B$ is a basis of $S$.

Step 2:
Apply G-sch to $B$ to obtain orthonormal basis $\mathcal E = (e_1,e_2)$ of $S$.

...

GO TO HELL

...

...

...

...

##### Matrix Decomposition

Last semester we decomposed matrices as $A=P^{-1}DP$, that was matrix factorization, and $A,D$ shared the same rank, spectrum. 
That was very situational as it was only for diagonizable matrices.

Then we do SVD and QR decomposition, which we can do for any of these matrices.

The goal is to decompose a matrix into simpler matrices.
What do we mean by simpler? Before we say diagonal and invertible are simpler.
Now we want to introduce other classes which behave nicely.

Let's have a convention which is very useful for us.
$(\forall z \in C) (\exists a,b \in R) z=a+ib$ 
Then $\overline z = a - ib$ 
Also, $\overline z z = |z|^2$

We consider matrices over field $C$. Since $R \subset C$, we can also technically consider real matrices as complex with a $0$ in the imaginary component.

$(A+B)^* = A^* + B^*$
$(\lambda A)^* = \overline \lambda A^*$
$(AB)^*=B^*A^*$
$(A^*)^*=A$

$<Av, w> = <v, A^*w>$

Subset of invertible matrices is useful for QR decomposition.

...

Recall $A \in M_n(C)$ is invertible $\iff (A_1,...,A_n)$ form basis of $C^n$.
We are interested in the orthonormal bases.

A matrix is called **unitary** if and only if $U*=U^{-1}$, as in $UU^* = I_n$.
Unitary matrices are a subset of invertible matrices.
Inverse of unitary matrix is very easy to achieve.
To check, just use definition. Don't inverse manually.

By theorem, a matrix is unitary if and only if $(\forall x, y \in C^n) ~~~ <UX, Uy> = <x,y>$
Note that $<Ax, y> = <x, A^*y>$.
Then $<Ux, Uy> = <x, U^*Uy> = <x,y>$

Note also $A_{ij} = <Ae_j, e_i>$  // ????????

Standard basis is orthonormal basis.
If vectors are not same, inner product is zero, otherwise, it is one.

The following is equivalent for $A \in M_n(C)$.
- $A$ is unitary
- The column vectors of $A$ form n orthonormal list in $C^n$
- The column vectors of $A$ form an orthonormal basis in $C^n$


...

We have two QR decompositions. Household and G-sch.

**Gram-Schmidt QR decomposition**
Theorem.
Let $A \in M_{m,n}(C)$ s.t. the columns of $A$ are linearly independent.
Then there exist:
- $Q \in M_{m,n}(C)$ with orthonormal columns
- $R \in M_{n}(C)$ upper triangular matrix.
such that $A=QR$

Upper triangular is when every entry below the diagonal is zero.

Let $(v_1,...,v_n)$ be an orthonormal list.
If $v \in span(v_1,...,v_j)$, then $(\forall i \in (j..n])~~v \bot u_i$ 

To find $Q$, we apply G-sch on $A$'s vector columns, as they are already LI.
We want to find list $(e_1,...,e_n)$ s.t. $span(e_1,...,e_n) = span(A_1,...,A_n)$

Side-note: Not only that, by theorem of G-sch,
$span(v_1,...,v_j) = span(e_1,...e_j)$.

Define $Q \in M_{m,n}(C)$ s.t. $Q_1=u_1,...Q_n=u_n$
Where $A_1 = <A_1, u_1>u_1$ etc.

And $R \in M_n(C)$ by $R_{ij}=<A_j, u_i>$
Then we claim $R$ is upper triangular, $A=QR$.
This is allegedly beautiful as we need to use everything we learnt up until now.
