
What is a change of basis matrix?
Change of basis...
All matrices are matrices but some are more matricy than others.

We have a matrix. We have a basis for $R^2$. The standard basis for example.
We have a standard basis for every $R^n$.
There are uncountably many bases for every vector space.

We look at every vector relative to our basis. 
If we consider some other basis, and then look at the coordinate vector, it will be different.
It will be the scalars which are needed such that $B (c_1,...c_n) = (v_1,..,v_n)$.

Given a vector in basis $B$, and another basis $B'$, how can I express the vector in respect to $B'$.
This translation itself is a linear map from the same vector space to the same vector space.

We should investigate the change of basis from an arbitrary basis to the standard basis. $[M]_{\mathcal B \leftarrow \mathcal E}$ 
We take the vectors of the matrix columns and place place them in the matrix.

An isomorphism takes a basis to a basis. 

A good property of the COB matrices is that $([M]_{\mathcal B \leftarrow \mathcal E})^{-1} = [M]_{\mathcal E \leftarrow \mathcal B})$
The matrix $M$ that is taking basis $\mathcal E$ to basis $\mathcal B$ 
How does one get the other way? Simply take the inverse.

If we consider the COB $[M]_{\mathcal B' \leftarrow \mathcal B}$
We can decompose to to $[M]_{\mathcal B' \leftarrow \mathcal E} [M]_{\mathcal E \leftarrow \mathcal B}$
We can use the standard basis as an intermediary.
// For example, like in Chemistry, we can use the mole constant as an intermediary. 

Then, this is just equal to $[M]_{\mathcal B' \leftarrow \mathcal E} ( [M]_{\mathcal B \leftarrow \mathcal E})^{-1}$

// Matrix multiplications are usually $3 \times 3$ in test

A few examples.
Given $\mathcal B = \{[1, -1], [1,1]\}$ and $\mathcal B' = \{[-2, -2], [-2, 2]\}$
Find the change of basis matrix $[M]_{\mathcal B' \leftarrow \mathcal B}$ .
$[M]_{\mathcal B' \leftarrow \mathcal B} = [M]_{\mathcal B' \leftarrow \mathcal E} [M]_{\mathcal E \leftarrow \mathcal B} = [M]_{\mathcal B' \leftarrow \mathcal E} [M]_{\mathcal B \leftarrow \mathcal E}^{-1} = \begin{bmatrix} -2 & -2 \\ -2 & 2\end{bmatrix} \begin{bmatrix} 1 & 1 \\ -1 & 1 \end{bmatrix}^{-1}$

The difference with last year is that this is a more general change of basis as opposed to coordinate vector spaces.

...

Selected topics from the sample test email.
###### Infinite dimensional vector space
Why are $F^{\infty}$ and $P(R)$ inf. dim.?
By definition, it is infinite dimensional $\iff$ there is no list that spans it.
Characterized by: for every natural number, we can find a linear independent list of that length.

Suppose there is a spanning list of length $n$. Then we pick some extra vector ( $n+1$ ) that is not spanned. Same concept with linear independence.
For polynomial space, it is infinite dimensional because for every list of polynomials, they have some maximum degree, so we can consider another polynomial with degree $n+1$, there is a polynomial of higher degree that is not spanned.
Linear independence wise we can construct the lists $1, x, ... x^{n-1}$
The field does not matter for $P(F)$.

Take the upward projection of the standard bases vectors of $F^n$ in $F^\infty$ to find a subspace of dimension $n$ of an infinite dimensional vector. After we get to $n$, we have infinitely many zeros afterwards. Similarly we can do that for $P(C)$ since they are isomorphic.

Examples of infinite dimensional subspaces of infinite dimensional spaces.
Detailed argument includes showing isomorphism. 
For example, this has to do with, for example, $F^\infty$ but all even entries are zero.
Then, it is isomorphic with $F^\infty$, therefore the dimension is the same. It is a subspace but it is infinite dimensional.
We need to show that we are bijective linear map. Injective zero kernel and definition of surjectivity or fundamental theorem for proving the rest.

Deciding if a given subset is a subspace (closed under additivity and mult.)
Contradicting a subspace is showing the lack of a zero but it cannot be able to prove.

###### Linear Dependence
What is the linear dependence lemma?
If we have some list of vectors, if there some vector that is a linear combination of some others vectors, then it is in the span of all the vectors before it UNION all the vectors after it.
If we cannot find such vector, list is linearly independent.

You should know at least one result in lecture 1 where we use the linear dependence lemma. As in, know one of the proofs for it.
###### Vector Space Sums
Know the formula of the sum of a vector space.
If we have two vector subspaces, then what is their sum? 
$U_1, U_2 \subset V$ , Then $U_1+U_2 = \{u_1 + u_2 ~|~ u_1 \in U_1, u_2 \in U_2\}$
Arbitrary $u_1, u_2$ and add them. All possible sums.
They are subspaces, so same field, but the dimension can be different. Padded with zeros.
The dimension of the sum is not the sum of dimensions, overlap.
Then, we invoke IN-EX.
The formula to compute the dimension of the sum is $\dim(U_1) + \dim(U_2) - \dim(U_1 \cap U_2)$.

###### Linear Map
Given a linear map from $V \rightarrow W$, prove that kernel and range are subspaces.
To prove kernel, it's all $v$ s.t. $Tv = \vec0$ we can see it preserves closures.
Then again, range also shows it, we show it with linearity. Additivity, Homogeneity are qualities of linearity.

Remember Fundamental Theorem of Linear Algebra.
""Can there be a linear map from this space to this space, with this kernel?""
And then we plug in the numbers.
There is a linear map $T$ from $R^5$ to $P_6(R)$ with $\dim(\ker(T)) = 2$ and $rank(T)=4$ .
By F. T. dimension of domain is equal to sum of dimension of kernel and rank.
$\dim(R^5) = \dim(ker(T)) + rank(T) = 2 + 4$ contradiction! 

Decide if vector spaces are isomorphic $\iff$ there exists an isomorphism between them. If they are of the same field, then if they have the same dimension, they are isomorphic, because they are isomorphic to $F^n$ and isomorphism is transitive.
To disprove isomorphism. Assume there would be an isomorphism and derive something stupid. Use qualities of inj., surj., and F. T.

Length of LI list, length of spanning list.

###### Matrix of linear maps...
The linear map between $F^n$ and $F^m$ all we have to do is plug the standard basis in the map and the output will be our new basis.
Essentially, see what the standard basis vectors map to and use it as columns to build the matrix. Take the output columns and throw them into a box, boom, matrix done. Linear maps are described entirely on what they do on the basis. If the images on the basis are the same, then they are the same map.
If two linear maps map the basis to the same thing, their matrices are the same.
That is why it's enough to construct a matrix.
We plug in basis, get new basis.

It's related if it's the same space, but this is more general.
Change of basis is an isomorphism, so the COB matrix is going to be an invertible matrix (and all that follows).

Compute matrix of $T: R^5 \to R^3$ defined by $T\begin{bmatrix} v_1 \\ v_2\\ v_3 \\ v_4 \\ v_5 \end{bmatrix} = \begin{bmatrix} v_1 - v_3 + v_4 \\ v_2 + v_3 \\ v_5 - v_2\end{bmatrix}$
Then, plugging in each and every vector of the basis.
We get that the columns are: $\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ -1 \end{bmatrix}, \begin{bmatrix} -1 \\ 1 \\ 0\end{bmatrix}, \begin{bmatrix} 1 \\ 0 \\ 0\end{bmatrix}, \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$ 
Thus the change of basis matrix is $\begin{bmatrix} 1 & 0 & -1 & 1 & 0 \\ 0 & 1 & 1 & 0 & 0 \\ 0 & -1 & 0 & 0 & 1\end{bmatrix}$
Obviously, it is not bijective. It is not injective, but it is surjective.

...

Know all proofs and results of lectures 1, 2.

...

It is true if $T$ is an injective linear map, then $T$ takes LI to LI.
It is true if $T$ is surjective linear map, then $T$ takes spanning to spanning. (Or show that we have a preimage for every element in codomain)
Apply the definition of LI. There are no nonzero scalars...
Use linearity and homogeneity.
Apply the definition of spanning. 
Use implication.

Linear map is injective $\iff$ kernel is zero.
Contradiction in both dimensions is what Marzieh likes.

...

There is a proposition we need to know for subspace dimensions.

...

Memorize proofs and results of lectures 1, 2.
