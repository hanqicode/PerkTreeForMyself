# Introduction and Transport Layer Services

A transport-layer protocol provides for **logical communication** between application processes running on different hosts.

By logical communication, we mean that from an application’s perspective, 
it is as if the hosts running the processes were directly connected.

Application processes use the logical communication provided by the transport layer to send messages to each other, 
free from the worry of the details of the physical infrastructure used to carry these messages.

Transport-layer protocols are implemented in the end systems but not in network routers.

## From Application Layer To Network Layer
On the sending side, the transport layer converts the application-layer **messages**
it receives from a sending application process into transport-layer packets, 
known as transport-layer **segments** in Internet terminology.

This is done by (possibly) breaking the application messages into smaller chunks and 
adding a transport-layer header to each chunk to create the transport-layer segment.

The transport layer then passes the segment to the network layer at the sending end system, 
where the segment is encapsulated within a network-layer packet (a **datagram**) and sent to the destination.

1. Application: message.
2. Tranport: segment.
3. Network: datagram.

## Relationship between Transport Layer and Network Layer
1. Transport: logical communication between application processes.
2. Network: logical communication between hosts.

## Overview of the Transport Layer in the Internet
Two distinct transport-layer protocols available to the application layer:
1. **UDP**: User Datagram Protocol. an unreliable, connectionless service
2. **TCP**: Transmission Control Protocol. a reliable, connection-oriented service.


