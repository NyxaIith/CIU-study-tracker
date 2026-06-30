---
title: Binary Numbers
status: Complete
tags: [topic/foundation, type/concept]
created: 2025-06-30
---

# Binary Numbers

## Overview

Binary is a base-2 number system. It uses only two digits: 0 and 1. Every piece of data a computer stores or processes — numbers, text, images, programs — is ultimately stored as a sequence of 0s and 1s.

## Why It Matters

Computers are built from transistors, which are tiny electronic switches that are either off (0) or on (1). Binary maps perfectly onto this physical reality. A computer cannot natively store the number 7 — it stores 0111 instead.

## Core Concepts

Each position in a binary number represents a power of 2, starting from 2⁰ on the right.

| Position | 2³ | 2² | 2¹ | 2⁰ |
|----------|----|----|----|----|
| Value    | 8  | 4  | 2  | 1  |

**Binary to decimal:** multiply each digit by its positional value and sum them.

Example: `1011` = (1×8) + (0×4) + (1×2) + (1×1) = **11**

**Decimal to binary:** repeatedly divide by 2 and record remainders from bottom to top.

Example: 13 → 13÷2=6 R1 → 6÷2=3 R0 → 3÷2=1 R1 → 1÷2=0 R1 → read upward: **1101**

## Examples

| Decimal | Binary |
|---------|--------|
| 0       | 0000   |
| 1       | 0001   |
| 5       | 0101   |
| 10      | 1010   |
| 15      | 1111   |

## Key Takeaways

- Binary is base-2. Only 0 and 1 exist.
- Each bit position doubles in value moving left.
- All computer data is binary at the lowest level.
- 8 bits = 1 byte. A byte holds values from 0 to 255. #flashcard

## Common Mistakes

Forgetting that position values start at 2⁰ = 1 on the right, not 2¹. The rightmost digit is always the ones place.

## Related Concepts

- [[03 Hexadecimal]]
- [[04 Boolean Logic]]
- [[09 How a CPU Works]]

## Practice
<!-- Link only: [[04 Practice/Foundation/Binary Numbers Practice]] -->

## Resources
