We last talked about the design of a modulo counter FSM.
Now, about the detection of a sequence.
We have a circuit that has one input and one output.
Binary numbers are coming to the input, and the circuit should detect three concurrent ones. Once the sequence is detected, it should be reset to one.

Something similar will be the assignment for the lab.
i.e. 
Input: `010111011111011011111111000`
Output: `000001000100000000100100000`

The output immediately depends on the input, so it is a Mealy-type FSM.

We need a state transition graph (STG) in this case.
We start with the initial state, denoted A.
When zero comes in the beginning, nothing happens, we are waiting for one. 
If 0 comes, we return to the same state.  I/O = `0/0`
However, if 1 comes, the first 1 is detected, we go to B, `1/0`.
If zero comes after the first one, we return to the first zero.
Same goes for the third one.
Otherwise, if we have `1/1`, we immediately report `1` to the output.
![[Pasted image 20260309135518.png]]

Next step, from STG, to Stage Transition Table (STT):
![[Pasted image 20260309135601.png]]

Output and next state respectively depending on the input and current state.

Let us talk again about state encoding. The aim is to assign binary code to each state. The condition is, every assignment must be unique - the states must have distinct codes.
Different possible encoding, binary encoding, for N states with need $log_2 N$ bits.
Every two neighboring states differ in one bit only, that's Gray code.

After the encoding, we construct a truth table from the encoded FSM.
![[Pasted image 20260309140642.png]]


We turn them into Karnaugh maps and find the SOP, and turn it into logic.
Don't forget to add the D-Flip-Flops into the circuitry!
![[Pasted image 20260309140622.png]]

...

We can also create a similar circuit but with the Moore-type, which is not dependent on the input directly. This is trivially Mealy-type as there is a wire connecting the input to the output directly.
In Moore, an additional state will substitute the logic we use for the input.
![[Pasted image 20260309140834.png]]

This time:
![[Pasted image 20260309140923.png]]


Thus, the final circuit will look as:
![[Pasted image 20260309141112.png]]



#### Timing Analysis
Now, the question is, what does the frequency of `CLK` need to be?
It depends on the gate types, technology, etc.
Fan-in (number of gate inputs), Fan-out (number of gate outputs), wire length.

![[Pasted image 20260309141420.png]]
Flip-Flop timing is really important.
Try to remember these terms, they will be needed and are useful to understand.

The data must be stable, prepared and present for storing near the D-input for a time before the rising edge, that is the setup time. 
Then, it should not disappear immediately after the clock, that is the hold time.
To calculate the delay, we use the Clock-to-Q - what is the delay of the flip flop, actually? From the rising edge, how much time does it take until the data propagates to the output?
We keep the hold time a bit longer than the C2Q.

In the Mealy type, we have information travelling from input to output, input to DFF, DFF to output, and DFF to DFF.

We calculate the sums of delays on all those paths, according to the gates and other logic. We take the maximum out of the different sums, and that will be our frequency. We adjust ourselves to the slowest part of our circuit, as to not race and leave it behind...
Nowadays the delays of gates are smaller, compared to delays on wired.

The delay depends on resistance and capacitance, which increase whenever we make the gate bigger, stronger. Technically the output would be faster, but the resistance and capacitance make it slower in general, so they have to balance a trade-off.