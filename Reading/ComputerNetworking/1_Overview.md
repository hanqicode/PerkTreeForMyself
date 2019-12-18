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
1. Processing delay: 
The time required to examine the packet’s header and determine where to direct the packet is part of the processing delay.
2. Queuing delay:
It waits to be transmitted onto the link.
3. Transmission delay:
Our packet can be transmitted only after all the packets that have arrived before it have been transmitted.
4. Propagation delay:
The time required to propagate from the beginning of the link to router B is the propagation delay.

## Protocol Layers
1. Application: **Message**. e.g. HTTP, SMTP, FTP, DNS. 
2. Tranport: **segment**. transports application-layer messages between application endpoints. e.g. TCP, UDP.
3. Network: **datagrams**. moving network-layer packets known as datagrams from one host to another. e.g. IP.
4. Link: **frames**. the network layer passes the datagram down to the link layer, which delivers the datagram to the next node along the route.
5. Physical: move the individ- ual bits within the frame from one node to the next.
