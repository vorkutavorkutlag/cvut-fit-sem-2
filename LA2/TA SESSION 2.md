
Properties of Linear Maps, abstract stuff...

We have to vector spaces, and we have a linear map between them, let's investigate its properties. 

$T: V \rightarrow W$.
We don't care if they're fin. or inf. as long as they are vector spaces.
Instead of focusing on $T$, we've been focusing on individual $V, W$.
Finite, infinite, subspaces.

The property of an infinite dimensional vector space is that there is no list that spans it. We can also think of it in the Linear Independence way. For every integer $n$, we can find a linear independent list of length $n$. If this holds, it is infinite dimensional also.

Using this same criterion, we can find finite dimensional vector spaces.

We can take out scalar multiples for a map and additivity.
Homogeneity:
Let $v \in V, c \in F$ then $T(cv_1) = cTv_1$
Additivity:
Let  $v, w \in V$ then $T(v+w) = Tv+Tw$

$T$ is a mapping, function. In finite dimensional linear mappings, it is a matrix. The only reason we are not interchanging it with a matrix is for non-linear maps and for infinite dimensional linear maps.

To prove a map is linear it just needs to satisfy homogeneity and additivity for an arbitrary input.

Properties include...
We know that $V, W$ has a zero vector.

Always, $T(0_V) = 0_W$. To prove...
$T(0_V) = T(0_V+0_V) = T(0_V)+T(0_V)$
Then subtract $T(0_V)$ from both sides
$0_W = T(0_V)$ 
Because $T(0_V)$ lives in $W$.
This is very easy in the finite dimensional vector space where every map can be represented with a matrix. $A\vec0 = \vec0$.

Consider $v_1$, and $v_2$ which is the additive inverse of $v_1$ in $V$.
$T(v_2) + T(v_1) = \vec0$
We want to show that a linear map preserves inverses.
Using linearity, $T(v_1+v_2) = \vec0$
The addition inside is happening in $V$.
Then, $T(\vec0)=\vec0$, which we have proven earlier, so we are finished.

...

Consider the map $S: F^\infty \rightarrow F^\infty$
Such that $S((a_0, a_1, a_2, ...)) = (0, a_0, a_1, a_2, ...)$
If we consider the scalar multiplication, this works out, because $c \cdot 0$ works out.
Also if we do the proof we see that additivity works too.

Injectivity.
For every two equal outputs, the inputs are equal. $f(x)=f(y) \implies x = y$
The notion of injectivity relates to the kernel.

Given a linear map $T: V \rightarrow W$
$ker(T) = \{v : V ~:~ Tv = \vec0\}$
The only difference from LA1 is that we are considering general vector space and general linear map.

If the map is injective, then the kernel is $\{\vec0\}$.
Assume injectivity.
Let $v_1, v_2 \in V$
Since we're injective, $Tv_1 = Tv_2 \implies v_1 = v_2$
To contradict, assume we have another element in kernel $c$. 
Then, $T(c) = T(\vec0) = \vec0$ 
But this contradicts with our injectivity assumption, since $c \neq \vec0$
So, it must be $\{\vec0\}$

If the kernel is $\{\vec0\}$, then the map is injective.
To contradict, assume it is not injective.
Then, we have $v_1, v_2 \in V$ s.t. $Tv_1 = Tv_2 \land v_1 \neq v_2$
$T(v_1-v_2) = \vec0 \land v_1 \neq v_2$ 
A nonzero element in our kernel!... So, the kernel is not the singleton zero.
So, we have the contradiction, and this holds.

Thus, $T$ is injective $\iff$ $ker(T) = \{\vec0\}$

...

Direct Sum.
Subspaces $V,W$ of some superspace.
We want to look at things in form $v+w$.
When we write $V+W=\{v+w ~:~ v\in V, w \in W\}$
Because these are both subspaces, they both contain zero, so we know the intersection of them will be at least the singleton zero.
If have intersection zero, we write the special notation:...
$V \oplus W$ is the set of $V+W$.
I don't know we will see later.

Everything they can cover together. Friendship is magic.

...
Keep in mind though that two vector spaces where one is $(x,0)$ and other is $(0,y)$ their direction some will result in $R^2$

Intersection of subspaces is a subspaces but union is not necessarily that.
