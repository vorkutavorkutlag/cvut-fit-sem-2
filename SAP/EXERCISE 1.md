
We may reduce $\overline a b \overline c + a \overline b c + abc$ to $b \overline c + ac$ by factoring out literals and their negations, where they become tautologies and get absorbed.
Alternatively, we may create a k-map and and find the prime implicant loops, and isolate them into a SOP.

Additionally, given a different canonical description $f(d,c,b,a) = \sum(3,11,12,13,14,15)$ 
Note: The order of the variables in the function has consequence on the k-maps, in particular when looking at MSB and LSB. Though, it has to be in the same order in the truth table or the reverse (?).
When we want to derive the sum of min-terms, we look at the rows at which the function is equal to one, and it will be the sum of those literals (and negations, if the literal's valuation is 0 in that index).
The sum of min-terms is not yet minimized.
We may minimize it algebraically by factoring out the common factors

$cd + ab + \overline bcd = ab + \overline b cd$
In the test, we will explicitly mention which bit is the most significant.


