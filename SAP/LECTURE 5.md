The aim of this lecture is to teach you the operation, names, notation of circuits and technologies within devices.
The simple circuits include gates such as XOR (eXclusive OR)
It is one when the number of inputs set to one is odd.
Also recognizable by the K-map being a checkerboard. No way to minimize. Difficult to implement, but strong component.
We can build XOR using 4 NAND gates, equivalent to 16 CMOS transistors.
Technically we can also implement it with 10, even 6 transistors with no other gates.
also $a \oplus b = a \overline b + \overline a + b$ 

It is not scaleable in the amount of inputs. Three input NAND can be implemented with less transistors than with two input NANDs. The only way to design that is with cascading XORs.

The majority function is equal to one when a majority of the input is equal to one. Has an odd number of inputs. Majority of three for example, after constructing truth table and k-map $M_3(c,b,a) = ab + ac + bc$ 

More complex combinational circuits include...
Encoders/Decoders convert data from one code to another. For example, converting binary code to "1 out of $N$" notation when encoding FSM states into binary.

Very important component is the multiplexer, MUX.
It is something that has several inputs, typically one output, and some selection signals. Those select which input will go to the output.
If the selection `s` is `0`, we choose the first input value. Otherwise, the other.

![[Pasted image 20260309192457.png]]

The implementation is pretty straight forward, from the high level behavioral description. Simple logic!

This operator is often called `ITE`, If-Then-Else.

We can have $n$ inputs, $log_2(n)$ selectors, and one output.

Actually implemented with binary $\rightarrow$ 1 out of 4 decoders.

We can even consider data buses for this. We for example can have 4 inputs, wherein each input carries 8 bits with it. Then the output is a single output that carries 8 bits.
Editor's note: ...implementation?


The demultiplexer, deMUX, does the opposite.
Generally one input, one select, two outputs. If selector is 0, then the first output will be assigned the input, otherwise, the second output will be assigned the input.
This of course works the same for $n$-inputs/outputs.

...

Let's recall the adders, repeat something, proceed.
The half adder has two inputs and two outputs, the sum and the carry (what goes to the next order).
It is very simple, wherein the sum is the $a \oplus b$ and carry is $ab$.

A full adder then adds three 1 bit binary numbers $(a,b,c_{in})$ and produces sum and carry, 2 bit output. It is completely symmetric.
The sum will be the xor of all of them, $a \oplus b \oplus c_{in}$
The `cout` will be equal to $ac_{in} + bc_{in} + ab$ also equal to majority $M_3(a,b,c_{in})$.

Naturally we can also form a full adder from two half adders.

Then we can have an $n$-bit adder from cascading $n$ full-adders.
That is the ripple carry adder.
A single half adder for the least significant bits, and then a full adder for every subsequent bit.

It works slowly. An adder is used everywhere, hardware implemented in every CPU, the most essential parts of every processor. It would be a pity if the adder were too slow. For 4 bits, it's fine, but for 128 bits we'd need 128 steps to do that! 
It can be solved with a two level implementation, carry look-ahead, etc.

One extreme is designing everything in one massive truth table (one massive component), and the other extreme is the ripple carry (a lot of small components).

The carry look-ahead adder "predicts" the carry and compute it separately. There is a different component that handles the carries. To generate a carry, bother operands need to be one.

...

Sequential circuits.

The most basic one, the **register**, is the D-Flip-Flop. It is a 1-bit synchronous sequential circuit memory. The term registers is used more often to talk about how the data flows.

We can have an $n$ bit register memory. A 4-bit register will have 4 primary inputs, 4 primary outputs, and another pseudo input for the clock.

Additionally, there may be registers with setting and resetting pseudo inputs. They will be setting the values of all bits to either one or zero.

Additionally, to allow store the data further, we may introduce an enable signal. If it is one, it is storing input, if it is zero, it is ignoring the input.
Implementation with MUX:
![[Pasted image 20260309195529.png]]


We can also denote a shift register. It has only one primary input, and possible more than one primary outputs. Data is shifted like a queue.
We may also enable it and disable it with the enable signal if we add it.

Editor's note: he asks us if we have any questions, but we are progressing so fast my mind hasn't even had the time to digest this and come up with any question.

...

Counters!
Increment, Decrement, Reversible (can count up and down!)
Types by code can include binary, decimal, modulo, gray, "1 out of $N$". 

The counters can be implemented using a FSM, first with STG, then STT.
Adding enable means the FSM is not autonomous anymore,.

We can generalize the $n$-bit counter by implement it with registers, plus an adder.
