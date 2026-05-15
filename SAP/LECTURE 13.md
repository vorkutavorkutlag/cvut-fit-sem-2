
# CPU Controller & Architecture

The control unit drives the cycle process

The CPU control unit is a finite state machine, FSM.
Runs in an infinite loop, driven by the instructions (opcodes) and the CPU state.
Inputs include opcode, and CPU control signals (ALU, registers, etc.)
Outputs include CPU control signals (to ALU, other timing and control signals)

Realization hardware is a hardwired control unit and a micro-controller.

Micorprogram control unit.
Usually, Sequential part is implemented by registers, Combinational as gate.

The sequential circuit, where combinational part is implemented in memory is the micropgoram memory.
The CPU instructions are divided into smaller microinstructions.
They from a microprogram microcode

The instruction set is the set of microprograms.
CPU firmware.

<small> We can change CPU firmware. </small>

Advantages include, the firmware can be changed, updated by reprogramming.
Even new instructions might be introduced after the CPU is deployed.
Possibility of patches.

Drawbacks include, it is slower and bigger.

Sequential circuit is implemented by memory.

We have a multiplexer, input of control signals, and then we choose which of these signals we take into consideration.

Microprogram control unit
Horizontal: Long microinstructions, shorter microcodes, several signals are controlled at the same time, more efficient HW utilization, more complex microprogram development
Vertical: shorter microinstructions, longer microcode, more like "normal" code.

### Pipelining

Isn't it a contradiction that some instructions takes a single cycle, but you need several cycles to go through the whole loop?

Pipelining.
Going through the instruction cycle. 
The idea of pipelining is the instruction cycle is a sequential process, one phase is executed by another.
Each phase is implemented by a separate hardware - the execution unit.

When one phase is being executed, the HW of the other phases is "idle". :/

The assembly line is the cure.
Instructions are processed sequentially, by small parts.
...and in parallel! The execution units are working in parallel, instructions are processed in parallel.

There's some problems when there's conflicting instructions.

```
cmp r16,r17
brge branch
```


The issue is primarily with branching.
Either we wait, 
Either we do, then roll-back otherwise,
Or we go both ways.

Also, we must wait until a value is done being written.

```
st X, r16
ld r17, X
```

Or, simpler,

```
add r16, r17
add r16, r18
```

In this case, we could.. not write to `r16`, simply add to a special place from an ALU.
Data Forwarding.

That is why we can execute an instruction in one cycle, even though we have these complicated things.

Superscalar CPUs are multiple units in one CPU
Multiple execution units.
Typically in ALU.
Adders, multipliers, etc.
Sometimes the whole units are duplicated ALU, FPU.

Multiple operations can be executed at the same time, in one clock cycle, +pipelining employed.

More hardware, distributing computation

### RISC
Reduced Instruction Set Computation

Simple instructions, typically executed in one clock cycle.
That is what we use in the AVR labs. 

The number of instructions can be large.
Reduced does not mean small number of instructions

Small number of instruction formats.
Small number of addressing modes.

Many registers.

Pipelining employed.
Hardwired control unit.

AVR, ARM, MIPS, SPARC, DEC Alpha.

### CISC
More complex.
Many addressing modes.
Small number of registers.
Strong interplay with compilers
Sometimes microprogram control unit.


Nowadays...
RISC is quite efficient in terms of architecture.
On the other hand, we have x86, and a lot of compilers build for it.
It would be difficult to abandon that architecture.
The implementation is not that efficient.
Well established architectures are CISC.

As a result, a RISC computer has hardware translation to a CISC x86 ISA (instruction set architecture)

x86, Apple CPU, etc.

# Error Detection and Correction Codes

This is essentially the basis for Secure Code.

The motivation.
Data transfer is not always safe, dependable.
Data transfer errors due to noise, imperfect manufacturing, cosmic radiation...
Remedy is :
- To know if an error happened, error detection codes (EDC)
- To correct a potential error, error correction codes (ECC)

We do not want to transfer or receive incorrect data.
General principle of codes.
More information than needed is transmitted for the above purposes.

It's not the hard copy of the data, it's an encoded data

General principles.
An $(n,k)$ block code.
- $n$; the length of the encoded information
- $k$; the length of the information to be encoded
- $(n-k);$ the number of check bits (i.e. added redundant information)

Vectors in play:
- The information to be transmitted
- The encoded information
- The received information
- The decoded information
- The error vector
- The error signature

The **hamming distance**, from K-maps, reappears now.
If we have two binary words, then the binary difference is the number of bits in which they differ.

A codeword is the encoded information (no error)
A non-codeword is when the encoded information is not valid (erroneous)
Affected by the error, and we can recognize it.

The code distance is the hamming distance between all codewords.
How many errors can we introduce, until it is no longer recognizable?
How many bits must be changed to obtain a different, valid codeword from another?

### Linear Codes

A linear code is of length $n$ and dimension $k$ is a linear subspace $C^k$ of the vector space $A^n$

The linear vector space is based on Galois field - $GF(2)$
Elements are 0,1 where Addition is XOR and multiplication is AND.

The generating matrix encodes it.
If we haven't obtained zero, there is an error.

A linear code $C$ detects $t$ errors $\iff$ its check matrix $H$ has $t$ linearly independent columns. As many detections as its rank.

A linear code $C$ corrects $t$ errors $\iff$ its check matrix $H$ has $2t$ linearly independent columns. As many corrections as twice its rank.

