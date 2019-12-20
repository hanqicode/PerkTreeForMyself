# Application Layer

## Terminology

### Processes Communication
A **process** can be thought of as a program that is running within an end system.

1. On one host
When processes are running on the same end system, they can com- municate with each other with interprocess communication, using rules that are governed by the end system’s operating system.

2. On more hosts
Processes on two different end systems communicate with each other by exchanging messages across the computer network.

### Socket
A process sends messages into, and receives messages from, the network through a software interface called a **socket**.

This is the interface between the application process and transport layer.

A process is analogous to a house and its socket is analogous to its door.

### Addressing Process
To identify the receiving process, two pieces of information need to be specified: 
1. the address of the host. (**IP address**)
2. an identifier that specifies the receiving process in the destination host. (**port number**)
