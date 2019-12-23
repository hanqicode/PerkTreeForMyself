# Multiplexing and Demultiplexing

That is: extending the **host-to-host** delivery service provided by the network layer to 
a **process-to-process** delivery service for applications running on the hosts.

## Demultiplexing
At the receiving end, the transport layer examines fields in segments to identify the receiving socket 
and then directs the segment to that socket.

## Multiplexing
The job of gathering data chunks at the source host from different sockets, 
encapsulating each data chunk with header information (that will later be used in demultiplexing) to create segments, 
and passing the segments to the network layer is called multiplexing.

## Segment Format

```
Source port number + Destination port number
Other header fields
Application message
```
