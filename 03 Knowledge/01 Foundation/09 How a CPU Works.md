---
title: How a CPU Works
status: Complete
tags: [topic/foundation, type/concept]
created: 2025-06-30
---

# How a CPU Works

## Overview

The CPU (Central Processing Unit) is the component that executes instructions. It performs all arithmetic, logic, and control operations. Everything a program does passes through the CPU.

## Why It Matters

Understanding the CPU explains why certain code is fast, how programs interact with hardware, and what concepts like threads, caching, and clock speed actually mean.

## Core Concepts

The CPU operates on a continuous loop called the fetch-decode-execute cycle:

1. **Fetch** — Read the next instruction from memory.
2. **Decode** — Determine what the instruction means.
3. **Execute** — Carry out the instruction.

Key components inside a CPU:

- **ALU (Arithmetic Logic Unit)** — Performs calculations and logical operations. Built from logic gates.
- **Control Unit** — Directs the flow of data and instructions.
- **Registers** — Tiny, extremely fast storage directly inside the CPU. The ALU reads from and writes to registers.
- **Cache** — Small, fast memory built into the CPU chip. Holds frequently used data to avoid slower RAM access.
- **Clock** — Drives the cycle. A 3 GHz CPU runs 3 billion cycles per second.

## Examples

When you add two numbers in code: the values load into registers, the ALU adds them, the result writes back. This happens in nanoseconds.

## Key Takeaways

- The CPU runs a fetch-decode-execute cycle continuously. #flashcard
- Registers are the fastest storage. Cache is next. RAM is slower.
- Clock speed measures cycles per second. GHz = billions of cycles per second.
- Modern CPUs have multiple cores, each running its own cycle.

## Common Mistakes

Confusing clock speed with overall performance. Architecture, cache size, and core count all matter alongside clock speed.

## Related Concepts

- [[05 Logic Gates]]
- [[10 Memory Hierarchy]]
- [[11 What is an Operating System]]

## Practice
<!-- Link only: [[04 Practice/Foundation/CPU Practice]] -->

## Resources
