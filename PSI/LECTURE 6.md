
// ...Late.

Two Armies' / Generals' Problem

When there is an unreliable link between two sources of information, it is difficult to agree on a truth.
The solution is to:
1. A sends a messenger with a proposal
2. B sends a messenger back with confirmation
3. But then, how does B know the confirmation was delivered? Then, A sends an acknowledgement messenger.
4. ...B has to send the acknowledge messenger back, etc.
it is impossible to synchronize this entirely.

In reality, it's solved by only letting one side acknowledge (superior source of truth).

Data delivery problems include packet loss, acknowledgement loss, and late acknowledgement.

Algorithms for flow control include **stop & wait** (sends data, waits for acknowledgement. if there is no ACK, wait and send again. There is big gap where we are not sending data, wasteful), **sliding window** (utilizing time while we wait for acknowledgement, send numerous packets without confirmation and resend if necessary. Zigzag pattern. The buffer in which it is sent without acknowledgement is called a window. Window size defines maximum n. of packets sent without ACK.)

Nowadays TCP uses selective repeat with fast-re-transmit and low error rate.
Confirmation contains which next piece of confirmation is missing, game-changer.
(As opposed to historical implementations.)
Usually, when 3 of the same acknowledgement are received, without timeout, it sends missing packet again.

Best, except, poor performance on links with high error rates. Go-back-N better then.

Backwards compatibility is the bane of networking.

TCP, UDP in transport layer differences and similarities - you know the drill.
