end systems / hosts / devices
access networks: first point (hop) of contact (of the device) towards the outer internet
	difference in speed and sharing between users/devices
	wireless: both local (wifi) and wlan have access points > devices connect to

transmission > aka packet switching
data is broken into packets of (L) bits, adding packet header to each chunk
transmits at a rate of (R) (capacity or bandwidth)

forwarding packets (aka switching) is local
it's a local action ditacted by a local forwarding table, first lookup, then forwarding

routing is global
global action, determine source-destination paths taken by packets
via routing algorithms

`traceroute` 3 probes per hop, measures rtt (round trip time

throughput: rate at which bits are being sent from sender to receiver
total speed of transmission regardless of each link's capacity
limited to the slowest link of the chain

---
TCP RFC https://www.rfc-editor.org/rfc/inline-errata/rfc793.html

![[Screen Shot 2022-04-29 at 18.51.01.png]]

each layer **encapsulates** the data from the prior and adds a header to serve whatever its protocol is in charge of

![[Screen Shot 2022-04-29 at 18.57.32.png]]

![[Screen Shot 2022-04-29 at 18.59.38.png]]

UDP is connectionless: doesn't verify that the receiver is listening or got the message

IP addressing packet delivery is also connectionless

---
**IP Addressing**

An IP address consists of 4 bytes (or octects, as in 1 byte = 8 bits) divided into two components: a network address and a host address. Based on the starting decimal number of the first byte, you can classify IP addresses as Class A, Class B, or Class C, as shown in Table 2-3.

![[Screen Shot 2022-04-30 at 14.20.41.png]]

class A: `net . node . node . node`
class B: `net . net . node . node`
class C: `net . net . net . node`

In addition to a unique network address, each network must be assigned a `subnet mask`, which helps distinguish the network address bits from the host address bits.

```
For example, a company has been issued two IP addresses: 193.145.85.0 and 193.145.86.0. Looking at the first byte of each address, the company determines that both are Class C addresses. With a default subnet mask of 255.255.255.0, 254 host addresses can be assigned to each segment. You use the formula 2^x - 2 for this calculation, with x representing the number of unmasked bits. For this exam- ple, x equals 8 because there are 8 bits in the fourth octet:
2^8 -2=254
```

you can’t give a user an address of 192.168.8.255 because it would produce all 1s in the host portion of an IP address; this address is reserved as a broadcast address to all nodes on the segment 192.168.8.0.

The router’s job is to take packets destined for a computer on a different network segment from the send- ing computer and send them on their way.

Hex numbers are sometimes expressed with “0x” in front of them. For example, 0x10 equals decimal number 16.

---

`topologies` (mesh/tree/star), `mediums` (ethernet/fiber/coax/wireless), and `protocols` (TCP/UDP/IPX) that can be used to facilitate the network

![[Screen Shot 2022-05-15 at 19.24.51.png]]

---
