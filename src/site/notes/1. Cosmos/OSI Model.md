---
{"dg-publish":true,"permalink":"/1-cosmos/osi-model/","created":"2025-06-02T16:57:03.703-04:00","updated":"2025-06-02T20:17:22.939-04:00"}
---

202506021657
Status: #idea
Tags: [[Networking\|Networking]]
State: #nascient
# OSI Model

The Open Systems Interconnection model is a 7 layer model that has been by the [[TCP/IP Model\|TCP/IP Model]], but that is still taught extensively because its concepts and ideas are core to the functioning of the [[TCP/IP Model\|TCP/IP Model]]. In fact, rather than seeing it as "obsoletion", it might be better to think of the [[TCP/IP Model\|TCP/IP Model]] as a pragmatical reimplementation of the [[1. Cosmos/OSI Model\|OSI Model]], in which case the importance of the OSI model is clear.

These 7 layers, still serve as the reference.

To remember the layers, just remember:
- All : [[Application Layer\|Application Layer]]
- People : [[Presentation Layer\|Presentation Layer]]
- Seem : [[Session Layer\|Session Layer]]
- To : [[Transport Layer\|Transport Layer]]
- Need : [[Network Layer\|Network Layer]]
- Data : [[Data Link Layer\|Data Link Layer]]
- Processing : [[Physical Layer\|Physical Layer]]

The [[TCP/IP Model\|TCP/IP Model]] basically takes the OSI model and condenses it to what network engineers care about. As a result, the last three layers (Application, Presentation, Session) are condensed to one single Application layer.

Then the [[Data Link Layer\|Data Link Layer]] and the [[Physical Layer\|Physical Layer]] who have very related functionalities (the data link layer checks for integrity of data from physical layer for example) are condensed to one [[Network Access Layer\|Network Access Layer]].

Finally, the [[Network Layer\|Network Layer]] which is fairly vague and could in theory represent any form of network is specified to be the [[Internet Layer\|Internet Layer]] (functionally they do the same thing though.)

As a result, the [[TCP/IP Model\|TCP/IP Model]] has 4 layers:
- [[Application Layer\|Application Layer]]
- [[Transport Layer\|Transport Layer]] (TCP layer)
- [[Internet Layer\|Internet Layer]] (IP layer)
- [[Network Access Layer\|Network Access Layer]]

**Some resources will represent the TCP/IP model has a 5-layer model by keeping the Data Link and Physical layer separate!***

## References
