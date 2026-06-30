---
title: Memory Hierarchy
status: Complete
tags: [topic/foundation, type/concept]
created: 2025-06-30
---

# Memory Hierarchy

## Overview

Computers use multiple types of storage arranged in a hierarchy. Faster storage is smaller and more expensive. Slower storage is larger and cheaper. The CPU pulls data up through this hierarchy as needed.

## Why It Matters

Every algorithm runs inside this hierarchy. Data that fits in cache runs much faster than data fetched from RAM. Understanding this explains why some code is slow even when the algorithm is correct.

## Core Concepts

From fastest to slowest:

| Level | Name | Typical Size | Typical Speed |
|-------|------|-------------|---------------|
| 1 | CPU Registers | Bytes | < 1 ns |
| 2 | L1/L2/L3 Cache | KB to MB | 1–10 ns |
| 3 | RAM | GB | ~100 ns |
| 4 | SSD | TB | ~100 µs |
| 5 | HDD | TB | ~10 ms |

**Registers** — Inside the CPU. Used directly by the ALU.
**Cache** — Built into the CPU chip. Copies frequently used RAM data for fast access.
**RAM** — Main memory. Programs run here. Wiped when power is off.
**SSD/HDD** — Permanent storage. Data survives power off. Much slower than RAM.

When the CPU needs data it checks each level in order. Failing to find it in a faster level is called a cache miss.

## Examples

If an array fits in cache, looping through it is extremely fast. If it does not fit, each access may require a round trip to RAM — roughly 100 times slower.

## Key Takeaways

- Faster memory is closer to the CPU and smaller in size. #flashcard
- Cache exists to avoid the speed gap between CPU and RAM.
- RAM is fast but temporary. Storage is slow but permanent.
- Writing cache-friendly code is a real and significant optimisation technique.

## Common Mistakes

Thinking RAM is the fastest storage available. Registers and cache are far faster — RAM is already three levels down the hierarchy.

## Related Concepts

- [[09 How a CPU Works]]
- [[11 What is an Operating System]]

## Practice
<!-- Link only: [[04 Practice/Foundation/Memory Practice]] -->

## Resources
