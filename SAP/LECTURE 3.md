
On Thursday, first lab test!
A minimization of a single k-map.

## Sequential Logic Circuits
#### ...and their Logic Synthesis

Logic circuits are described either by the vector of inputs and outputs, or a single input and output.
The difference between combinational and sequential, is that in comb. circuits, the output depends on the (immediate) input only, deterministic.
In sequential circuits, the output depends some previous events, meaning a sequence of inputs.
Memory is involved, explicitly (sync) or implicitly (async)
History is remembered, and feedback is involved.

The formal model will be the Finite State Machine (FSM), not to be confused with the automata. We will describe it using State Transition Graph (STG), State Transition Table (STT)

Definition of the FSM. It is a 6-tuple $(X, Y, Q, Q_0, \delta, \lambda)$:
- $X$ - the set of input symbols
- $Y$ - the set of output symbols
- $Q$ - the set of states
- $Q_0$ - the initial state
- $\delta$ - $X \times Q \rightarrow Q$ transition function
- $\lambda$ - $X \times Q \rightarrow Q$ output function.

We have a **Moore-type**, where the output depends on the state only, and a **Mealy-type**, where the output depends on the input and the state.

The less common FSM types include the autonomous FSM, which has no input, and the Medvedev FSM, which has no output.

The Moore-type's STG consists of nodes (status + outputs), and edges (input values).
The Mealy-type STG consists of nods (states), and edges (input values + output values)

From the graphs we can easily draw/read the function, so it's easier for us, but for processing, it's easier to transform the STG into a table, STT.
We have as many rows as there are states. They say the conditions for switching a state, and the logic for the output.
![[Pasted image 20260302191918.png]]

The example we used in the lecture is a counter modulo 4.
It has 4 states, 4 possible values for the modulo. So, we don't need any input for this for example, it is an autonomous state machine.
It counts from 0 to 3 by itself and then resets to zero.
The FSM 6 tuple:
- $X$ - no inputs
- $Y$ - outputs: $\{0,1,2,3\}$
- $Q$ - set of states ($Q_1,Q_2,Q_3,Q_4$) 
- $Q_0$ - initial state

This also classifies as the Moore-type.
First we draw the STG, and then we consider the STT.
![[Pasted image 20260302192407.png]]

Each output corresponds directly to one state.
We may encode the states into binary as well.

How do we store memory? We must learn it.

From async to sync sequential circuits, and flip flop...

###### Synchronous
The circuit is synced by an external (global) signal, say a clock. The circuit operates at a given, consistent frequency.
It has explicit memory, controlled by the clock, flip flops and latches.
For example, the `3GHz` label on the CPU, which is a sync circuit.
Downside is, it has to be as slow, as the slowest component in the chip. 
It cannot be any faster, as then the other component "would not make it".
###### Asynchronous
No explicit synchronization, no global clock.
In some families, there is explicit memory, but not in general.
When compared to synced circuits, these are larger, could be faster, consume less power, difficult to test and have routing problems.
It is difficult to construct them. While some CPU's have been built with them, some issues such as the difficulty to test them led to not being mainstream.

There are many types of async circuits. Different design styles, different principles..
The general properties are that there is no global clock, and sequential behavior is ensured by feedback.

The simplest one is the **R-S latch**, our leading example guiding us right now.
![[Pasted image 20260302193205.png]]
These are NOR gates
Two inputs, two outputs. These outputs, as a warning, look like Q and Q negated, is needs not be exactly like that, it's just a bad notation.

Editor's note: which one of these runs first?? Isn't this circular reasoning? We talked about this being a problem in DBS today for example..
Outcome: Even though there is a loop, it is stable. Even though the output of this gate, depends on the output of the other gate, it goes in a loop, we can clearly calculate it. But, in some cases, say if both inputs are zero, there will be an issue.

![[Pasted image 20260302193710.png]]

They remember!
It remembers the state as such.
If we build the circuit in logisim, it will work, for example.

![[Pasted image 20260302193802.png]]
For 0,0 it remembers, then sets, then resests.
In other implementation of R-S latches there could be some problems.

Now, from async to sync!
The memory was not complicated but it was difficult to control.
Let us now introduce the **Gated RS-Latch**
![[Pasted image 20260302193928.png]]
Where `E` is the enable symbol.

We can make it even simpler. Setting these latches to zero or one was pretty complicated, and we can do with just two inputs, called a **Gated D-Latch**
![[Pasted image 20260302194104.png]]
The `D` comes from `Data`
When the Enable is zero, the data ignores. Otherwise we just write the D to it.

The $\overline Q$ is mostly useless and is just used for the circular input into $Q$, we don't use its truth table values most of the time.

Now, we can minimize it into NAND gates.
![[Pasted image 20260302194336.png]]

Side-note: this looks like a sigil, ancient peoples were on something. Is this real? LOL

**MASTER SLAVE DYNAMIC (flip-flop)** is when we use the clock (CLK), to say that storing/writing data happens in a single instant,
![[Pasted image 20260302194521.png]]
When CLK = 0, data from D is copied to the Master, when CLK = 1, data from Master is copied to Slave.

So, a single clock cycle to change the $Q$ on the right. Up, to change the intermediary $Q_M$, and then down, to change $Q$. Has to go up then down.

We must set the input to some particular value, put the clock up, put the clock down, and then the value will be visible (and remembered!) on the other side.
Instead of Enable, we have clock, marked with a small triangle and CLK.

The **Clock** is a global synchronization signal, it is periodical, and is generated by a  RC quartz oscillator. The rising edge and falling edge are the turning the clock to 1 and then back to 0 respectively. The gap between two rising edges / the gap between two falling edges is called the clock period $T [s]$, and the clock frequency is then $f = \frac{1}{T}[Hz]$.

In real life, we may have a number of different clocks running at different frequencies. Different parts of the CPU's are working at different (still prescribed) frequencies.

To summarize,
- Basic 1-bit memory elements in sequential circuits.
- The async latch has no synchronization, just data inputs, e.g. RS-Latch
- Gated latch has a sync signal (Enable, CLK), is Level sensitive (0, 1).
- Flip-Flop uses a sync signal (CLK), is Edge sensitive (rising edge, falling edge).
- The most commonly used is the D flip-flop, (DFF).

###### Hardware Model of Sync Sequential Circuits
Based almost entirely on D-Flip-Flops.

We can divide any sequential circuit into a combinational part, and some other memory that is controlled by the clock (flip flops). 
The inputs coming from outside are called primary inputs (PIs), outputs going outside are called primary outputs (POs), inputs/outputs going into and out of the memory are the pseudo-primaries respectively (PPIs/PPOs).

Sequential design consists of a couple of phases.
- Designing the STG (+problem analysis)
- State minimization (equivalent states that can be merged can occur) - Will be skipped
- STT derivation
- State assignment (binary encoding codes to states)
- Designing truth tables, k-maps, ... (combinational synthesis)
- Timing analysis (deriving the maximum frequency)
- Retiming (improving speed by moving flip flops) - Will be skipped

![[Pasted image 20260302200156.png]]


In the MOD 4 counter, we will need 0 PIs (as it is autonomous), 2 POs (output consists of 2 bits), and 2 DFFs (as the states are stored in 2 bits).

The combinational logic builds the new state, and then the DFF remembers it.

