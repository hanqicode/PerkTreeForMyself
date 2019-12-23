# Principle of Reliable Data Transfer

## RDT 1.0: Over a Perfectly Reliable Channel
We first consider the simplest case, in which the underlying channel is completely reliable.

There is no need for the receiver side to provide any feedback to the sender since nothing can go wrong!

Note that we have also assumed that the receiver is able to receive data as fast as the sender happens to send data. 
Thus, there is no need for the receiver to ask the sender to slow down!

## RDT 2.0: Over a Channel with Bit Errors
A more realistic model of the underlying channel is one in which bits in a packet may be corrupted.

Raise an analogy between Phone Contact with our Protocol:

| Phone Contact | Protocol                 |
|---------------|--------------------------|
| "OK"          | Positive Acknowledgments |
| "Sorry"       | Negative Acknowledgments |

In a computer network setting, reliable data transfer protocols based on such retransmission are known as **ARQ (Automatic Repeat reQuest) protocols**.

Three additional protocol capabilities are required in ARQ protocols to handle the presence of bit errors:
1. **Error detection**. Like: checksum.
2. **Receiver feedback**. Like: positive(ACK) and negative (NAK).
3. **Retransmission**. A packet will be re-transmitted by the sender.

**What about when ACK/NAK is corrupted?**

If ACK/NAK is corrupted when sender receives the feedback from receiver, what should we do?
1. "What did you say?" - But this can be corrupted again.
2. Re-send. - It will introduce duplicate packets. But sender can add sequence number to solve this problem.
3. More checksum. - Receiver is able to detect error and even recover the packet.

## RDT 3.0: Over a Lossy Channel with Bit Errors
In addition to corrupting bits, the underlying channel can lose packets as well.

### How to deal with packet loss?
Sender wait *certain* time (like timeout) and assumes the packet is lost.

But it is hard to choose a reasonable value. 

Sender in practice will choose a value and the sender may re-transmit the packet even though 
neither the data packet 
nor its ACK 
have been lost.

This will intruduce **duplicate data packets**, but happily, we have sequence number to handle such case.

So sender needs a **countdown timer** to implement such time-based retransmission mechanism.

## Summary
There are several important concepts here:
1. checksum
2. sequence number
3. timer
4. ACK/NAK
