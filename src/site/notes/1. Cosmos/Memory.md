---
{"dg-publish":true,"permalink":"/1-cosmos/memory/"}
---

202407200308
Status: #idea
Tags: [[1. Cosmos/Computer Architecture\|Computer Architecture]], [[Operating Systems\|Operating Systems]]
State: #nascient
# Memory
The way we store and retrieve daa for later.

The data is encoded in bits. (01010000100101101111)

# Volatile Memory
They need constant power to maintain their data. Once turned off, they basically reset.
## Primary Memory (Dynamic Random Access memory D.RAM)
The place instructions and data that's needed in the now is stored.
The cells in this type of memory can be accessed in any order, which is why it's called **random**. Still slow compared to the next type.

Each [[Transistor\|transistor]] is associated with a [[Capacitor\|capacitor]], and will keep their charge for a long as the capacitor is on. So capacitors need to be recharged for memory retention.
## Cache (Static Random Access Memory)
Fastest memory. No capacitors

# Permanent Memory
![Pasted image 20231024073241.png](/img/user/The%20Vault/Pasted%20image%2020231024073241.png)
## Secondary Memory
- Slower than Primary Memory
- Retain Data Permanently
- Bigger in size
- Cost-effective
- Semi-Random Accessibility.


# The Big Picture
![Pasted image 20231024073812.png](/img/user/The%20Vault/Pasted%20image%2020231024073812.png)
The CPU doesn't know the Second Memory exists, this is all handled at the OS level.

Cache is the phone pocket of the CPU, where frequently accessed instructions are stored for quick retrieval. The Main Memory is the todo-list stored in his backpack. It can access it quickly, but not faster than his phone. 

It can communicate with it, by adding info, removing info, creating new stuff, etc.

The CPU doesn't know the secondary memory is a thing. So think of the Secondary Memory as the subconscious of the CPU, which puts relevant info in the Main Memory when needed, and saves it back to the Secondary Memory for permanent storage in ways the CPU itself cannot fathom.

## Memory Interfacing
![Pasted image 20231024083520.png](/img/user/The%20Vault/Pasted%20image%2020231024083520.png)

Multiple types of memories can be ranked. The higher they are the less time it takes to access them, but the more costly it is. 

Memory Interfacing is the part of the architecture which worries about how to maximize the MIPS (Million of Instruction per Second) while keeping the cost under reasonable levels. How to connect the processor to varying levels of memory and IO peripherals.

**Jargon**:
Hit : Processor searched for an instruction/data in one memory and found it.
Miss: Processor searched but didn't find it, implies we need to search in a lower tier of memory.

### Way 1: All Levels of Memory are connected to Processor at once
![Pasted image 20231024084308.png](/img/user/The%20Vault/Pasted%20image%2020231024084308.png)

### Way 2: Interface the Memory as a Cascade
![Pasted image 20231024084346.png](/img/user/The%20Vault/Pasted%20image%2020231024084346.png)

At a glance it seems way 1 is more efficient. But we wait to see further teaching.

## Multiple Caches? It makes sense to talk of multiple caches for multicore processors.
Nah, but there are multiple levels.

L1 : Embedded in CPU from start
L2 : First in MOBO, but now in CPU
L3 : Is shared between all cores.

L1 is smallest but fastest, L2 stored less important data that is still frequently accessed, L3 is shared across all cores.

## Two ways to decide what goes in cache

Spatial Locality : If an insftruction is somewhere in memory, it is more likely this information is nearby in memory

Time Locality : If an instruction is accessed, it is more likely it will be accessed again.


## Direct Memory
**Jargon**
Word : Smallest addressable element in memory
Block : Some grouping of words within the Main Memory. In a given memory all blocks are the same size (contain the same amount of words), and the elements they contain is contiguous
Line : Identical to a block, except in the cache.

The size of word is calculated in bytes
The size of a block is calculated in words or bytes as well.
The size of a line is the same as a the size of the block in the same system.

#computerengineering #mylearning 


## References

