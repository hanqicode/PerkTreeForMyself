# Basic Architecture
Link: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-basic-architecture.html

SQS is a distributed system.

When sending a message to the queue, the queue redundantly stores the messages across multiple Amazon SQS serviers. 
(For high availability)

## Standard Queues

### TPS
Standard queue support a nearly unlimited number of transactions per second(TPS) per API action.

### Message Order
A standard queue makes a best effort to preserve the order of messages, but more than one copy of a message might be
delivered out of order.

### At-Least-Once Delivery
Amazon SQS stores copies of your message on multiple servers for redundancy and high availability.
On rare occasions, one of the servers that stores a copy of a message might be unavailable when you receive or delete a message.

If this occurs, the copy of the message isn't deleted on that unavailable server, and you might get that message copy again
when you receive messages. 

Design your applications to be **Idempotent** (they should not be affected adversely when processing the same message more 
than once).

## FIFO Queues
FIFO (First-In-First-Out) queues are designed to enhance messaging between applications when the order of operations and event
is critical, or where duplicates can't be tolerated.

### TPS
By default, FIFO queues support up to 3,00 TPS, per API action.

### Message Order
FIFO.

### Exactly-Once Processing
No duplicates.

### Compatibility
Clients: Async Client doesn't support FIFO queues.
