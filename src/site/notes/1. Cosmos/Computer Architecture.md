---
{"dg-publish":true,"permalink":"/1-cosmos/computer-architecture/","created":"2025-01-22T11:17:14.035-05:00","updated":"2024-07-20T03:08:15.869-04:00"}
---

202407200307
Status: #idea
Tags: [[1. Cosmos/Computer Architecture\|Computer Architecture]]
State: #nascient
# Computer Architecture
Design of computers


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/1-cosmos/intstruction-set-architecture-isa/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">





202407200308
Status: #idea
Tags: 
State: #nascient
# Intstruction Set Architecture (ISA)

Defines the instructions which a computer can operate and how they should interact with each other. How they function at the machine level is left to the [[1. Cosmos/Hardware System Architecture (HSA)\|Hardware System Architecture (HSA)]]

## References


#mylearning #computerengineering

</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/1-cosmos/hardware-system-architecture-hsa/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">




202407200307
Status: #idea
Tags: [[1. Cosmos/Computer Architecture\|Computer Architecture]]
State: #nascient
# Hardware System Architecture (HSA)

Design of how the CPU, and IO peripherals and other computer components will interact with each other.

Does not force an implementation, this is left to [[1. Cosmos/Computer Organization\|Computer Organization]], architecture really only specifies the higher overview of how the higher level components should interact with each other.

## References


#mylearning #computerengineering #universitynotes

</div></div>


# Multiple ways to classify computer architectectures.
## 1. Von Neumann Architecture and Non-Von Neumann Architecture

## Von Neumann Architecture (Princeton Architecture)
What you're already used to. 
Sequential (one instruction at a time). Three way connection between CPU, Memory and I/O Peripherals. 

Data and Instructions are stored in the same place. This causes a problem that a computer cannot read instructions and data at the same time. Often referred to as the Von Neumann Bottleneck.

## Non-Von Neumann (Harvard Architecture)
Really similar, but with two memory units, one to store the instruction and one to store the data. Processor can now do instruction reading and data reading at the same time, which makes it faster.


## Modified Harvard Architecture
Some kind of unholy child between the two? I don't know he didn't explain it much.

Apparently a widespread type now. The CPU now has cache (small but really fast memory) and is not forced to read from memory at all times. The Memory is still split into two main parts Instruction and Data Memory (but the instruction part can also contain secondary data).

## 2. Flynns Taxonomy.
### SISD (Single INstruction stream, Single Data stream)
one instruction at a time, one output at a time. The Von Neumann Architecture is of that type.
### SIMD (Single Instruction stream, Multiple Data Stream)
Thanks to multiple ALUs being used, the system can now execute multiple operations at the same time. Since there's only one control unit, it's merely going to be the same instruction done to all inputs.

### MISD (Multiple Instruction stream, Single Data stream)
More of a theoretical thing, since no one implements those on their own. The idea is you can do multiple things at once to one piece of data.

### MIMD (Multiple Instruction stream, Multiple Data Stream) (Multiprocessors)
Multiple instructions can be done at once. Since there are multiple processors, each processor can do it's own thing.



## References


#mylearning #computerengineering #universitynotes