Linear map may be proven to be injective if it:
- has the zero kernel
- takes every LI to LI
- takes every basis to LI
- ...definition of injectivity...

Should be finite dimensional.

$B=(v_1,v_2,v_3)$
$T: V \to W$
$(Tv_1, Tv_2, Tv_3)$ is LI.
Claim: $\ker(T) = \{\vec0\}$

$v \in \ker(T) \implies v= c_1v_1 + c_2v_2 + c_3v_3$
$\implies Tv = \vec0 \implies c_1Tv_1 + c_2Tv_2 + c_3Tv_3 = 0$ // linearity
$c_1 = c_2 = c_3 = 0 \implies v = \vec0 \implies \ker(T) = \{\vec0\}$

Assume kernel is not zero. Then it should have a basis. And then it should take it to LI. However image is zero. So we get a list of zeros, which is LD. Contradiction.

In order to construct linear mapping it is enough to determine its action on the basis.

If we want to construct surjective.
We want to fix a basis and show it sends every basis to a spanning.

Remember theorem about surjective/injective mappings domain/codomain dimension inequality.