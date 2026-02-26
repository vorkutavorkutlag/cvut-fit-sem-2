To be mathematically explicit about which function grows faster, we will be using new notations of Big O and Little o.
The notation is, for example, $x \in O(2x) x \rightarrow +\infty$ 
Also, $x^2 \in o(x^3) x \rightarrow +\infty$

The definition is: $f \in O(g) x \rightarrow a$ 
If **exists** positive constant $C$ and exists neighborhood of point $a$, such that 
$|f(x)| \leq C \cdot |g(x)|$ 
Formally, $$(\exists C > 0) (\exists U_a) ~~ |f(x)| \leq C \cdot|g(x)|$$
Then, Little O is smaller. We find for **every** C a neighborhood $a$, and the different is strictly less than.
Formally, $$(\forall C > 0) (\exists U_a)~~ |f(x)| < C \cdot |g(x)|$$

`1.34)` prove $\frac{1}{x} \in O(1) x \rightarrow +\infty$ 
By the definition, we need to find a positive C and a neighborhood $U_{+\infty}$ 
A neighborhood of infinity is the interval from any value to infinity.
We want to prove, essentially. $\frac{1}{x} \leq C |1|$ 
Because $x \rightarrow +\infty$ we are "near" infinity, we can concentrate on positive values and omit the absolute value. Then we have $\frac{1}{x} \leq C$
We can now chose parameters $C := 1, ~~~ U_{+\infty}(1, +\infty)$ 
One over anything from that interval is less than or equal to one.
And this is true. Big O is way easier to prove.

`1.42)` prove $2x^2-2 \in O(x-1) x \rightarrow 1$
From the definition, $(\exists C > 0)(\exists U_1) ~~~ |2x^2-2| \leq C |x-1|$ 
Note that we can choose any neighborhood, any epsilon, no matter how small or big.
For example, we can use the neighborhood $U_1 = (\frac{1}{2}, \frac{3}{2})$ 
$2|x^2-1| \leq C|x-1| \implies 2|x-1||x+1| = C|x-1| \implies 2|x+1| \leq C$ 
For example, with this given neighborhood, we may simply choose $C := 10$
Thus, for any number in the interval, we the expression will always be true.
Editor's note: What's stopping us from choosing absurdly small epsilons and absurdly large C's?

`1.33)` prove $2(x-1)^3 \in o(3(x-1)^2) x \rightarrow 1$
From the definition, $(\forall C > 0)(\exists U_1) ~~~ |2(x-1)^3| < C|3(x-1)^2|$
For every positive constant, we need to find a (possibly different) neighborhood.
Notice also that the statement is now strict (strictly less).
It's always better to work without absolute values so let's try to get rid of them.
$2(x-1)^2|x-1| < 3C(x-1)^2 \implies 2|x-1| < 3C \implies |x-1| < \frac{3}{2}C$ 
The absolute value is the distance from the zero. So, $|x-1|$ is the distant of $x$ from the number one. Now, we don't want to be further than that number!
$1-\frac{3}{2}C ... 1 ... 1+\frac{3}{2}C$ will be our interval, we have found our neighborhood for every C.
The neighborhood will be $U_1 = (1-\frac{3}{2} C , 1+\frac{3}{2}C)$
Notice also how we can use the positive constant in the neighborhood's definition.

`1.40)` prove $f \in o(g)x \rightarrow +\infty$
Where $f=3x^3-x+1$ and $g(x) = 4x^4 + 2$
By definition, $(\forall C > 0)(\exists U_{+\infty}) ~~~ |3x^3-x+1| < C|4x^4|+2$
We want to find a chain of inequalities such as $|3x^3-x+1| < ... < ... < ... < |4x^4+2|$
That is the beauty of inequalities. 
First, let note that $4x^2+2$ is always positive. Also, $4x^4 < 4x^4 + 2$ at all times.
Because we are going into infinity, we can assume that $x>1$. In that interval, $x^3>1$.
Now we can say $|3x^3-x+1| < |3x^3-x+x^3| = |4x^3 - x|$
- Side-note, the inequality $|A+B| \leq |A|+|B|$  might come in handy
Then, $|4x^3-x| \leq |4x^3| + |x|$. And we can also say then $|4x^3| + |x| < |4x^3| + |x^3| = 5|x^3|$
Finally, we have to prove that $5|x^3| < 4x^4$
Once more remember we are working on interval $x \in (1, +\infty)$ so we can divide by by $x^3$.
Oops, seems like we forgot to write the $C$'s during the solution. Imagine they're there. At last the inequality is $x > \frac{5}{4C}$ and the neighborhood $U_{+\infty}=(\frac{5}{4C}, +\infty)$ 
But note also we have to combine it with the condition $x > 1$.
Then we have to find the intersection. $U_{+\infty} = (MAX\{1, \frac{5}{4C}\}, +\infty)$

On the fourth week of tutorial, maybe March 12th, we are going to have a little test in this room. One exercise, 15 minutes, to get extra points, going into the exam, not assignment. 2 points. 
If we know the definition, it's 1 point, if we get the correct answer overall, 2 points.