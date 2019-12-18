# Overview of Computer Networking

## Internet
A host -> segment data -> packet(data + header) -> B host.

## Protocol
A protocol defines the format and the order of messages exchanged between two or more communicating entities.

## Hosts
End systems are also referred to as hosts because they host (that is, run) application programs.

## Transimission
Most packet switches use **store-and-forward** transmission at the inputs to the links.

A link must receive whole packet data first and can foward it to next link.

## Queuing Delay
Each link has an output queue.

If an arriving packet needs to be transmitted onto a link but finds the link busy with the transmission of another packet, 
the arriving packet must wait in the output buffer.

## Packet Loss
Since the amount of buffer space is finite, 
an arriving packet may find that the buffer is completely full with other packets waiting for transmission. 
In this case, packet loss will occur:
1. either the arriving packet
2. or one of the already-queued packets will be dropped.

## Packet Switching VS Circuit Switching
No reservation VS reservation.

Packet switching can support more users at the same time.

## Delays
