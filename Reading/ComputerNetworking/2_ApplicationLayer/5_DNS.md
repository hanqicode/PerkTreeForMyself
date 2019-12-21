# DNS

Domain Name System: The internet directory service.

## Motivation
Host can be identified by:
1. Hostname: *www.amazon.com*.
2. IP Address: *121.7.106.83*.

People prefer to use hostname; while routers prefer to use IP address.

In order to reconcile these preferences, we need a directory service that translates hostnames to IP addresses.
Then here is DNS.

## Definition
The DNS is:
1. a distributed database implemented in a hierarchy of DNS servers.
2. an application-layer protocol that allows hosts to query the distributed database.

The DNS protocol runs over **UDP** and uses port 53.

## Details
DNS adds an additional delay — sometimes substantial — to the Internet applications that use it.

The desired IP address is often cached in a “nearby” DNS server, 
which helps to reduce DNS network traffic as well as the average DNS delay.
