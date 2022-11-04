---
layout: wiki
title: network
cate1: Basis
cate2: Network
description: network
keywords: Basis
---

## the term

**TCP** (Transmission Control Protocol)

Transmission Control Protocol, a connection-based service.

**UDP** (User Datagram Protocol)

User Datagram Protocol, a connectionless service.

**IP** (Internet Protocol)

Internet protocol, information transfer mechanism.

## TCP

> TCP is a streaming device, a virtual connection. From the establishment of the TCP connection to the normal end of the connection, all data should be regarded as a whole, which ensures that the whole sent by the sender and the whole received by the receiver are consistent. Until the TCP is disconnected, the receiver does not know how much data the sender sends, how to improve it, and how much data there is. Therefore, in applications, there should be no assumptions about how TCP delivers data.

### Sliding window

![tcp sliding window](/images/wiki/tcp-sliding-window.png)

### Three-way handshake

![three-way handshake](/images/wiki/three-way-handshake.png)

### Four waves

![four-way handshake](/images/wiki/four-way-handshake.png)

## Difference between TCP and UDP

1. Connection-based and connectionless

2. Requirements for system resources (more TCP, less UDP)

    * TCP provides more complex control processes such as connection status, sending and receiving status, and timeout retransmission
    * TCP header is 20 bytes more than UDP's 8 bytes

3. UDP program structure is relatively simple

    Because the stream is continuous and ordered, TCP needs to handle the framing of data by itself, while UDP receives one packet at a time, preserving packet boundaries.

4. Streaming Mode and Datagram Mode

    * TCP guarantees data correctness, UDP may lose packets
    * TCP guarantees data order, UDP does not

5. TCP uses sliding window protocol for flow control

6. The logical communication channel of TCP is a full-duplex reliable channel, while UDP is unreliable

7. TCP connections are point-to-point, while UDP runs one-to-one, one-to-many, many-to-one and many-to-many interactive communications

UDP is suitable for communication or broadcasting that requires high-speed transmission and high real-time requirements, and TCP is suitable for scenarios that emphasize data sequence and reliability.

## refer to

* [The difference between TCP and UDP](http://staff.ustc.edu.cn/~mengning/np/linux_socket/new_page_13.htm)
* [Is it possible for sockets to lose packets under the TCP protocol? ](https://www.zhihu.com/question/53960871)
