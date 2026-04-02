
Note that $n^b \ll a^n$, $n^b \in o(a^n)$, $\lim_{n \rightarrow \infty} \frac{n^b}{a^n} = 0$ statements are equivalent.
Exponential is way way quicker than quadratic, cubic, etc.
Slow over quick the limit is zero.

`3.44.b)` $\lim_{n \to \infty} \frac{\sqrt[3]{n} - 3^n}{\cos(n^8) + 2^{-n}+n!}$ 
In this case, we are always trying the "quickest" element in denominator and nominator, factoring out.
$=\lim_{n \to \infty} \frac{3^n (\frac{\sqrt[3]{n}}{3^n} - 1)}{n!(\frac{\cos(n^8)}{n!} + \frac{2^{-n}}{n!}+1)}$ 
Most of these terms go to zero. Bounded times zero, or asymptotic hierarchy.
$=\lim_{n \to \infty} \frac{-3^n}{n!} = 0$
Slow, over fast, goes to zero. Again, refer to asymptotic hierarchy.

// $log_a n \ll n^a \ll b^n \ll n! \ll n^n$

In proper analysis, we would need to pedantically prove this, but in this course we can use the hierarchy rule.

Recall also $\ln(ab) = \ln a + \ln b$ and likewise in division.

`3.46)` $\lim_{n \to \infty} \frac{\ln(3^n+5)}{\ln(4^n-2)} = \lim_{n \to \infty} \frac{\ln(3^n(1+\frac{5}{3^n}))}{\ln(4^n(1-\frac{2}{4^n}))}$
$= \lim_{n \to \infty} \frac{\ln(3^n) + \ln(1+\frac{5}{3^n})}{\ln(4^n)+\ln(1-\frac{2}{4^n})} = \lim_{n \to \infty} \frac{n \ln 3}{n \ln 4} = \frac{\ln 3}{\ln 4}$ 

Again, professor made it easier, so we can have these "shortcuts".

For future reference, also, $a^n = e^{x ln a}$

