# FTP

## Motivation
User wants to transfer to/from a remote host.

In order for the user to access the remote account, the user must provide a user identification and a password.

The FTP client process in the local host to establish a **TCP** connection with the FTP server process in the remote host.

## Details
FTP uses two parallel TCP connections to transfer a file, a **control connection** and a **data connection**.
- Control connection: sending control information, like user identification, password, etc.
- Date connection: actually send a file.

## State
The FTP server must maintain **state** about the user.

The server must associate the control connection with a specific user account, 
and the server must keep track of the user’s current directory as the user wanders about the remote directory tree.
