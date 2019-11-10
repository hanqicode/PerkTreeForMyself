# Networking

## Examining And Monitoring A Network
`ping`: Sends a special network packet called **ICMP ECHO_REQUEST** to a specific host.

Most network devices receiving this packet will reply to it, allowing the network connection to be verified.

1. `ping google.com`.
It will print in terminal after press `ctrl + c` to exit, like:
```
PING google.com (172.217.3.174): 56 data bytes
64 bytes from 172.217.3.174: icmp_seq=0 ttl=47 time=3.480 ms
64 bytes from 172.217.3.174: icmp_seq=1 ttl=47 time=6.351 ms
64 bytes from 172.217.3.174: icmp_seq=2 ttl=47 time=5.563 ms
64 bytes from 172.217.3.174: icmp_seq=3 ttl=47 time=3.670 ms
64 bytes from 172.217.3.174: icmp_seq=4 ttl=47 time=4.037 ms
64 bytes from 172.217.3.174: icmp_seq=5 ttl=47 time=3.011 ms
^C
--- google.com ping statistics ---
6 packets transmitted, 6 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 3.011/4.352/6.351/1.196 ms
```

## Transporting Files Over A Network
`ftp`(File Transfer Protocol): is used for file download.

It is NOT secure because it sends account names and passwords in plaintext.

`scp`(Secure Copy Protocol): to copy file between hosts on a network. It uses SSH for data transfer and provides the same security as SSH.

In macbook terminal:
1. `scp qqihan@<timber_host_name>:/tmp/qqihan/logs.txt     /Users/qqihan/Desktop`
2. `scp -r qqihan@<timber_host_name>:/tmp/qqihan/             /Users/qqihan/Desktop`

## 
