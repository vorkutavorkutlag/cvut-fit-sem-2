Typically, logic = digital = switching = boolean.
Switched on, switched off. 
In contrast to analog, where the domains are continuous.
We can have multi-valued logic actually, as a side-note.

Today we are going to speak about combinational circuits (output depends on input only), sequential circuits (has "memory")

A **canonical** description of a function.
If a description is called to be canonical, it means that if we have two descriptions, of a single function, then these are isomorphic - equal.
A description could be a truth table, k-map, visualization in a boolean hypercube. 
Boolean expression is not canonical in general.

As a reminder, there exist different logic functions.
single-output, m-output, remember on-set and off-set.
on-set is all the "vertices" (specific row in the truth table) which evaluate to true. off-set is the opposite. 

A variable is input, output, or internal variable `{0,1}`
A literal is a variable or its negation.
Boolean space space is a space of $n$ variables.

For every boolean space of dimension $n$, we have $2^n$ logic functions.
For $n$ inputs, we have $2^{(2^n)}$ functions.

A boolean expression is a literal or an expression by application of a boolean operation to boolean expression(s) - recursive definition.

**SOP**, Sum of Products, also called DNF, Disjunctive Normal Form.
Usually called SOP.
It is a sum (OR) of product terms (AND), called cubes.
If a product term of $n$-variable function has $n$ variables, it is a **min-term**

**POS**, Product of Sums, also called CNF, Conjunctive Normal Form.
Usually called CNF.
It is the product (AND) of sum terms (OR) called clauses.
If a sum term of an $n$-variable function has $n$ variables, it is a **max-term**.

We can describe a list of min-terms as a sum of the indices wherein the function evaluates to a truth with the notation $\sum (3, 5, 6, 7)$  (the indices are an example).
This is called **SOM**, Sum of Min-Terms.
A sum of min-terms is also a canonical description of the function, as we can reconstruct it uniquely from this.

Also, text next week!

Let us come to **Logic Synthesis** - more of the practice than theory.
Logic synthesis is a step above the gates, but below the RTL (register transfer level). We are above the logic equations and finite state machine, but below the data flow.
It is the process of transformation of a higher level circuit description to a gate level. As in, from truth tables to gates - this is what we will do.
The aims are to minimize area, delay, power consumption, cost, etc. Possibly maximize reliability, testability, security, etc.
Logic optimization, minimization, is making the gate level description "better" with respect to the objective(s).

There are different ways of doing logic synthesis and optimization, typically based on the representation used.
From now on, **SOP synthesis and optimization** will be assumed.

From cubes to boolean algebra.
Let us take the adder for example.
Looking at the truth table of the full adder, inputs include $a, b, c_{in}$, outputs include $c_{out}, s$ 
Looking at the $c_{out}$, it is equivalent to some SOP.
A min-term is:
- A product of $n$ variables (or their negations) for an $n$-variable function
- Equivalent to one point (**vertex**) in 3D space

A K-map is a 2D transcription of a boolean space. 
The idea is, neighboring map cells are neighbors in boolean space. Also, two neighboring cells can be merged.
The purpose is to derive the smallest expression. This task is very complex in general, and it is double-exponential with the amount of inputs.
To minimize, find the largest "loops" - boolean cubes.

If there is a bar over that row/column in the k-map, it means that respective variable's value is set to 1. Wherever that bar does not cover, that respective variable's value is set to 0. Note that the 0's are omitted, left empty in the table.

The most essential thing - what is this good for? 
It is meant to derive the minimum SOP.
The idea is, we are merging neighboring cells.
Those vertices in the boolean space, that are neighboring, could be merged, because of the applied rules of boolean algebra, for example $a \overline b c + a b c = a c$ .
If the hemming-distance, the difference between these tow vectors, is only one bit, they are neighbors in the k-map, and can be merged.

Merging 1-min-term, making loops.
The rule is, the size of the loop must be in powers of $2 (2^i)$ where $i$ is the dimension of the resulting cube, $2^i$  min-terms are covered.
If the dimension is 0, there is only one min-term.
If the dimension is 1, we have 2 min=terms
If the dimension is 2, we have 4 min-terms, etc.

How to say what term it corresponds to? 
Being common means the value is the same across every "slot" in the loop.
Being uncommon means the value differs between some "slots" in the loop.
Commons can be negated or positive.
Then, we say that the result is the product of the commons, and we negate the negated products.

Making a loop of the size of, for example, three is strictly forbidden.

Editor's note: When setting the dimension of the loop to the entire hypercube, we won't have any commons, naturally. Then what will be the result of our minimization?? huh..

Inclusion, cover.
We write $abc \subseteq ac$ when all the min-terms of the term are included in the other one..

Cover of a function.
Two level SOP minimization - looking for the cover of the function.
Cover F of a function.
Such a set of cubes, so that the whole function on-set is covered by them.
A set of terms, cubes that covers all the 1's.
$F = \{c_1,..,c_k\}; f = \sum_{i=1}^k c_i$ 

These terms (cubes $c_i$) imply the functional value 1.
They are called **implicants**.
When a term is equal to 1, it implies the function is equal to 1.
It covers some 1's.

A redundant cover/cube is when it is not needed. For example, the aim of the minimization is to cover all the onset. If we can do it via two loops for example, then any more loops are not needed.

An irredundant cover F of a function.
Means no cube can be removed from the cover...

(**PI**)
A prime implicant is an implicant that is the biggest one in the cover.
It cannot be enlarged, and no literal can be removed from it.
It is not included in any other implicant.

(**EPI**)
A prime implicant that covers at least one 1-min-term, which is not covered by any other implicant. A prime implicant that is present in all minimum covers.
All essential prime implicants have to be in a minimum solution -but the opposite does not generally hold.

The aim of two level minimization is looking for prime and irredundant cover. Note, it is not unique, and prime and irredundant cover does note ensure minimality, just irredundancy.

Editor's note: How are minimality and irredundancy different from one another?
Outcome: We are looking for the irredundant prime cover, and irredundancy does not imply minimality. Mostly, we won't come to examples where it is not equal, but it is not equal in general.
If it is prime and irredundant means you cannot remove any literal from any term - the term cannot be made smaller in the map and smaller in the equation.
Nothing is said about the minimality of that as it can be done entirely in a different way which could be possibly better. 


Incompletely specified functions will be important for the lab.
In some cases, it could happen that we do not have some values in the map, in the function. So until now we had just 0's and 1's, but maybe we don't care about some values (DCs). 

We are going to design a decoder as a combinational circuit to the display later in the lab. We do not care what the value should be for 10, 11, 12, etc.

Incompletely specified functions are defined by Sum of Min-Terms and an exclusion sum for example $\sum_X(1,6)$  .

The cover may cover X's, must cover all 1's, and must not cover any 0's.

Implicants may cover 1's and X's, must cover at least one 1's, must not cover any 0's

There may exist some implicants that are not included in the optimum solution as they include DCs.

We have learned the basics of boolean/logic optimization, how to do it in K-maps. 