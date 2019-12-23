# UDP

In fact, if the application developer chooses UDP instead of TCP, then the application is almost directly talking with IP.

Note that with UDP there is no handshaking between sending and receiving transport-layer entities before sending a segment.
So UDP is said to be **connectionless**.

DNS is an example of an application-layer protocol that typically uses UDP.

## When uses UDP?
Many applications are better suited for UDP:
1. Send message as soon as possible(chat). TCP will throttle when links between client and server become excessively congested.
2. UDP does not introduce any delay to establish a connection. TCP has three-way handshake before it starts to send data.
3. UDP does not maintain connection state. A server can support more active clients for UDP over TCP.
4. UDP header(8 bytes) is smaller than TCP header(20 bytes).

## Reliable UDP
It is possible for an application to have reliable data transfer when using UDP.

This can be done if reliability is built into the application itself (for example, by adding acknowledgment and retransmission mechanisms).

This is not an easy work but application processes can communicate reliably without being subjected to the transmission-rate constraints imposed by TCP’s congestion-control mechanism.

## UDP Segment Structure
The UDP header has only four fields, each consisting of two bytes. Totally 8 bytes.

```
Source Port Number + Destination Port Number
Length + Checksum
Application Message
```

- Length: specifies the number of bytes in the UDP segment(header plus data).
- Checksum: used by the receiving host to check whether errors have been introduced into the segment.
