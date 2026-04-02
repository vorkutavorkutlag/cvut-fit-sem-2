
The main motivations to define abstract vector spaces was to keep track of scalar multiplication, additivity, etc. We define the properties and then define the abstract vector spaces. 

We again want to look at $R^2$, $R^3$ since we have more properties than scalar multiplication and vector addition.
We have for example dot product, and the orthogonality of the vectors, the angles between two vectors.

If we have two vectors in $R^2$, we have an angle $\theta$ between them. To compute it, we use the dot product.
If the angle is a right angle, 90 degrees or $\pi/2$, then we say the vectors are orthogonal.
To define the length of the vector we have something similar to the Pythagorean theorem, the square root of the sum of the squares.

We define the dot product $(x_1, y_1) \cdot (x_2, y_2) = x_1x_2 + y_1y_2$.
Importantly for us, two vectors are orthogonal $\iff$ dot product is zero.
$v_3 \perp v_1 \iff v_3 \cdot v_1 = 0$ 

Instead of $R^n$ we have an abstract vector space.
We really need that the vector space is over $R$ or $C$.
Then, for the notions of the **dot product**. We will generalize as the **inner product**.
The **length**, then, is going to the **norm**.
The length, being $\sqrt{v\cdot v}$ according to our definition of dot product. 

We look at the scalar mult, vec. add. and then we look at the abstract vector spaces.
We look at which parts of these properties we should pick to generalize it.

We also have the relations between the length and dot product, and we want to see if there is any relation between the norm and inner product.
That is the topics of our discourse.

We look at the orthogonality. Especially, we look at orthogonal bases.
In finite dimension, we say that we can find the orthogonal bases (if something, missed it), which then can help us with factorization and other important computations and algorithms.

Look at properties of dot product. Look at $R^2$
If we have $v \cdot v$ where $v=(x,y)$ then it is equal to $x^2 + y^2$
A property we can say is that $v \cdot v \geq 0$ always.
Then, we can always say $v \cdot v = 0 \iff x^2+y^2 = 0 \iff x=y=0 \iff v = \vec0$
Reminder, $v \cdot v$ is the length of $v$

We also have the distributivity property with dot product.
$v \cdot (v_1 + v_2) = vv_1 + vv_2$ 

And also scalar multiplication.
$v(\alpha v_1) = \alpha (vv_1)$
The proofs are trivial. We can obtain it by def. $v_1v_2 = x_1x_2 + y_1y_2$

Additionally, $v \cdot w = w \cdot v$
We did it for real numbers, we can also do it in $C$.
However, in case of complex numbers, $v_1=(z_1,w_1)$, $v_2 = (z_2, w_2) \in C^2$
We need to be careful. The dot product has to be a real number. The length must be a real number. 
If we define it by $z_1z_2 + w_1w_2$ that will be a complex number, but we need it to be real.

We can simply use the conjugate.
If $z \in C$ then $z = \alpha + i\beta$ and $\overline z = \alpha - i \beta$

So instead we define:
$v_1v_2 = \overline z_1 z_2 + \overline w_1 w_2$ 
And then we see $v_1v_1 \geq 0 = |z_1|^2 + |z_2|^2$
This is because $z \overline z = |z|^2$

So basically we do this to get a real length in case of $v_1=v_2$.
We will deal with the angle and orthogonality later. Right now we just defined this.

It is also possible to define by moving the conjugate.
$z_1 \overline z_2 + w_1 \overline w_2$ 

Definitions vary between these two mostly.

Instead of dot product, we want to call these generalizations inner product.
We look at these mappings as $V \times V \rightarrow F$ Where the field is either real or complex.

We satisfy properties positivity, definiteness (size = 0 $\iff$ zero vector), additive in the first slow, homogeneity in the first slot, conjugate symmetry.
$<v_1,v_2> = v_1 \cdot v_2 = z_1 \overline z_2 + w_1 \overline w_2$  

Note that $\overline{z+w} = \overline z + \overline w$, $\overline{\overline z} = z$, $\overline{\alpha z} = \overline \alpha \overline z$ 

Then we have also $<v,w> = \overline{<w, v>}$, conjugate symmetry.

In real number it is equal, but in complex number we need conjugacy.

We should have only one slot for additivity and homogeneity.
I.e. $<v+v', w> = <v,w>+<v', w>$
And $<\alpha v, w> = \alpha <v, w>$
It doesn't necessarily have to be the first, it can be the second, but never both.
We can define inner product in $C^n$, $R^n$ .

In $R^n$:
 $<\begin{bmatrix} x_1 \\ ... \\ x_n\end{bmatrix}, \begin{bmatrix} y_1 \\ ... \\ y_n \end{bmatrix}> := x_1y_1 + ... x_ny_n$
In $C^n$:
$<\begin{bmatrix} z_1 \\ ... \\ z_n\end{bmatrix}, \begin{bmatrix} w_1 \\ ... \\ w_n \end{bmatrix}> := z_1 \overline w_1 + ... + z_n \overline w_n$

Maybe we consider also matrices?
For this we need the concept of a trace. For every matrix, if $A$ is a square matrix on a field, we can denote trace of $A$, $tr(A)$, as the sum of diagonal entries. 
$tr(A) = a_{11}+...+a_{nn}$
Essentially, we can look also as a map $tr: M_n(F) \to F$
Is $tr$ a linear map? Yes, it is. Satisfies additivity, homogeneity. 
The only linear map from $M_n(F) \to F$ is the trace.
In infinite dimensional matrices the trace is even more important.


Definition in $M_n(R)$:
$<\cdot,\cdot> : M_n(R) \times M_n(R) \to R$
$<A,B>:=tr(B^TA)$ 
Transpose of $B$ times $A$, and then take the inner product.

Exercise: The above formula defines an inner product. Show that:
- $A\cdot A \geq 0$, $<A,A> = 0 \iff A = \vec0$
- $<A+B,C> = <A,C> + <B,C>$
- $<\alpha A, B> = \alpha <A, B>$
- $<A, B> = <B,A>$

If no one thought about it, she won't solve it, and it will be included in our exam (evil!)


Definition in $M_n(C)$:

We introduce another matrix for each matrix, called adjoined.
For $A \in M_n(C)$ we call $A^*$ the adjoined matrix. First we put a transpose, and conjugate.
$\begin{bmatrix}1 & i \\ 2 & 3+1 \end{bmatrix}^* = \begin{bmatrix}\overline 1 & \overline 2 \\ \overline i & \overline{3+i}\end{bmatrix}$  
If all of them are real numbers, then $A^* = A^T$
$A^*=(\overline{a_{ji}})$

So we define $<\cdot, \cdot>: M_n(C) \times M_n(C) \to C$
$<A,B> = tr(B^*A)$

In real case we consider transpose, in complex consider the transpose, then conjugacy in all entries - the adjoined.
This is important in computations in numerical analysis.

// why does the trace represent inner product? looks like a coincidence.

...

(?)
If we want to define inner product on polynomials, we have to use concepts of integration. $<p,q> := \int_0^1{p(x) \overline{q(x)}dx}$   

Another definition:
An inner product space is vector space $V$ along with an inner product.
Denoted $<\cdot, \cdot, >$
// What?

Some propositions for inner product space $(V, <\cdot, \cdot>)$.
- We have the linearity in the first slot. From definition.
- $<\vec0, v> = <v, \vec0> = 0$ for every $v \in V$
- $v=\vec0 \iff <v,w> = 0 ~~~\forall w \in V$
- $\forall v,w \in V ~~ v =w \iff <v,z> = <w,z> ~~\forall z \in V$
Good exercise prove the last one.
Note that it only makes sense with the last quantifier. At least one $z$ is not enough. Maybe they are two distinct angles that simply share the same angle with that one vector.

We also have:
$<v_1, \alpha w_1 + w_2> = \overline{<\alpha w_1 + w_2, v>} = \overline{\alpha <w_1,v> + <w_2, v>} = \overline \alpha <v,w_1> + <v, w_2>$

Abstract proof: $<0,v> = <0+0,v> = <0,v> + 0,v> \implies <0,v>=0$

...

As for the length.
Instead of length of a vector, we write the norm $||v||$ 
In $R^2$, it is $\sqrt{x^2+y^2}$. mathematically, the length means there is a map $R^2 \to R^+ \equiv [0,\infty)$.
Where, for every vector, we associate its length. If a vector is zero, then its length is zero. 
When we want to reach one point, A B C, It's shorter to go AC then ABC.
$||v+w|| \leq ||v|| + ||w||$
Additionally, $||\alpha v|| = |\alpha| ||v||$

The Euclidean max norm is different than the normal norm. $||(-1, -1)||_{\max} = 1$ whereas $||(-1,-1)|| = \sqrt 2$.

...

Q: Can we define a norm using inner product space?
In a vector space we can have more than one inner product $(V, <\cdot,\cdot>)$
In particular, formula $||v|| = \sqrt{<v, v>}$ defines a norm on $V$?
Then we can define a norm on the matrices as well.

Cauchy-Schwartz inequality, $|<v,w>| \leq ||v|| ||w||$

Norm max cannot be induced by any inner product.

$R^2$ with norm max is a normed space but not inner product space.
I am very confused about this topic I accidentally stopped paying attention.

Next week we will introduce orthogonality, seeing that the orthogonal basis behaves well.

For the test, lecture 1 lecture 2 are the topics.

...

If a vector space is isomorphic to a fin. dim vector space it too should be fin. dim. this arises from fundamental theorem.
Isomorphism is also exclusive to vector spaces under the same field.
Not all infinite dimensional spaces are isomorphic to infinite dimensional.

If one is fin. dim. the other is inf. dim. then there is no isomorphism.
If both fin. dim, check if the dimension is the same. If it is, they are isomorphic. if it is not the same, they are not isomorphic.

To prove infinite dimension, either show no list spans it, or show that we can find an LI list for every $n$.

No need to prove linearity unless explicitly asked.

$P(C)$ is infinite dimensional, cannot be isomorphic with finite dimensional.

...

$V,W$ over $F$.
Consider $L(V,W) = \{T: V \to W ~:~ T$ is a linear map $\}$
We claim $L(V,W)$ is a vector space.
We want to introduce vector addition, scalar multiplication, zero, etc.

Scalar mult:
$(\forall \alpha \in F)( \forall T \in L(V,W)) ~~~ \alpha T \in L(v,W)$ 
It should be a linear map $\alpha T : V \to W ~~~ v \to \alpha Tv$ 
That is linear, so $\alpha T \in L(V,W)$

Everything can be a vector space! Vectors can be cows if we, the creators, define (to our liking!) what $\alpha \cdot MOO$ is!

$T, S \in L(V,W) \implies T+S \in L(V,W)$
It takes $v \to Tv + Sv$ which is linear.
Additive inverse of $T$ is $(-1)T$ 
Zero vector is a zero map.

So, $L(V,W)$ is a vector space over $F$.

...

Given $V = F^n, W=F^m$ and bases $B, C$ respectively.
We can find isomorphism
$L(V,W) \to M_{m,n}(F)$
$T \to [T]_{C \leftarrow B}$ 

$\dim(L(V,W))=\dim(V)\cdot\dim(W)$ 
This is proof we can understand a linear mapping by some matrix.
It depends on the bases we fix for the vector spaces.

The coordinates of the vectors are related to isomorphisms.

Say which of the exercise proofs are hard or not.