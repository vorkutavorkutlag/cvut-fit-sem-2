
# Basics of Logic & Synthesis

Hardware are the material things, the Software is the program instructing the software. Rewritable memory is the breakthrough.
(ROM - Read Only Memory; sometimes...)
Digital - discrete vals, Analog - continuous values.
Embedded systems are all appliances that include logical electronics.
Something, driven by processor (CPU).

Computer hardware includes processor, memory, peripherals (keyboard, mouse), inerfacing (communication protocols).
There are different abstraction levels. You could look at individual transistors. Zoom out, look ate high lever description. Nowadays, hardware is designed in C.
Then, synthesis translates the HDL to the physical components.

Software includes operating systems, firmware (hardcoded instructions, BIOS)
Abstraction levels present here also. High level language, into assembly, into machine code (binary), into control signals.

#### Basic architecture 
Consists of CPU with Control Unit, ALU - wired into memory - wired into I/O
Instructions and data stored in the same memory. (no explicit difference)
Linearly organised memory (same size cells, RAM).
Binary representation of signals.
Instructions are executed one after the other. Can be changed with jumps.

There exists a Harvard alternative, being data and program memory is separated.
This might be in the test!!

#### Logic Synthesis
Every circuit has inputs and outputs.
First level of de-abstraction, for example, "output 1 iff both input is 1" $\implies$ AND gate.
Sum of two numbers, an Adder, is long addition in binary. i.e. carrying over 1's to next binary point. (1+1=10 carry to higher order)
Often, we can design circuits via truth table.


How to design truth table as hardware?
Mathematics will help. Boolean Algebra.
A variable, input, is 0,1. Literal - variable or its negation.
$B^n$ is a space of variables (size  $2^n$).
Every dimension is more variables, more possibilities.

Boolean functions include:
$f(X): B^n \rightarrow B$
$f(X): B^n \rightarrow B^m$
onset subset of vertices evaluating to 1, offset subset of vertices evaluating to 1.
Basic operators include disjunction, conjunction, negation, non-equivalence (XOR).
No explicit priority.

DNF, now known as SOP, sum of products, can be used to calculate $c_{out}$ in the adder.
If at least two out of three, it is TRUE.

Multiplication synonymous with AND, Addition synonymous with OR in boolean.

We can minimize expressions using logic laws. 
Neutrality, negation absorption, etc.

Karnaugh maps are 2D projection of n-dimensional boolean spaces.
Neighbors in boolean space are neighbors in Karnaugh maps (Hamming distance = 1).

From algebraic expressions to implementations.
Boolean expression to hardware is implemented through gates. Adder can be made matching with gates. Can be minimized with three level implementation.
Each gate can be implemented with a CMOS transistor(s).

Avoid AND, OR. NAND, NOR are smaller.