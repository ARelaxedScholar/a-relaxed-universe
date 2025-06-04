---
{"dg-publish":true,"permalink":"/1-cosmos/encapsulation/","created":"2025-06-02T17:10:07.568-04:00","updated":"2025-06-02T20:16:28.052-04:00"}
---

202506021710
Status: #idea
Tags: [[Networking\|Networking]]
State: #nascient
# Encapsulation

## In Networking
As data goes through the [[1. Cosmos/OSI Model\|OSI Model]] layers or better the [[TCP/IP Model\|TCP/IP Model]] layers, each layer after doing its checks will add data pertaining to its own functions. Typically headers (added at the front of the package), or trailers (added at the end).

We call these data packages [[Protocol Data Units (PDUs)\|Protocol Data Units (PDUs)]]. Each time we add a new set of header and trailers, we get a new PDU.

As data traverses the application-presentation-session layer, it is simply called "data".

Then it reaches the transport layer, where we will add the source and destination ports giving us a [[Segment\|Segment]].

Then we pass that segment to the [[Internet Layer\|Internet Layer]]/[[Network Layer\|Network Layer]] which will add the source IP/destination IP along with other niceties to the package, giving us an IP [[IP Packets\|packet]].

Then that will further be passed to the [[Data Link Layer\|Data Link Layer]] (where switches operate), so that we can be even more granular and specify where the data should go at the machine level by specifying the [[MAC Address\|MAC Address]], often also called the [[Burned-In Address\|Burned-In Address]]. The so obtained PDU will be called a [[Frame\|frame]].

Finally, will come the time to send that data over the wire, or waves, at which point we are dealing in [[Bits\|bits]].

This entire process DOWN the chain is called encapsulation.

On the other end, the reverse process UP the chain (where we strip the data of its headers), which is naturally done when the data you send is received (usually by some other device) is called [[De-Encapsulation\|De-Encapsulation]].

## References
