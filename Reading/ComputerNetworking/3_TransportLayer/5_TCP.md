# Connection-Oriented Transport: TCP

TCP: the Internet’s transport-layer, connection-oriented, reliable transport protocol.

## How does TCP setup connection?

From client to server:
1. The client application process informs the client transport layer that it wants to establish a connection to a process in the server.
2. TCP in the client then proceeds to establish a TCP connection with TCP in the server. 
3. Client sends a TCP segment.
4. Server sends a TCP segment.
5. Client sends a TCP segment.

Because three segments are sent between the two hosts, this connection-establishment procedure is often referred to as a **three-way handshake**.

## Flow control
This is different from **congestion control**.

TCP provides flow control by having the sender maintain a variable called the **receive window**.
The receive window is used to give the sender an idea of how much free buffer space is available at the receiver.

Why TCP needs flow control?

Because TCP receiver does not read the segments in sender buffer ASAP.
