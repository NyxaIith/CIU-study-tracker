---
title: Logic Gates
status: Complete
tags: [topic/foundation, type/concept]
created: 2025-06-30
---

# Logic Gates

## Overview

Logic gates are physical electronic circuits that implement boolean operations. Each gate takes one or more binary inputs and produces one binary output. Billions of these gates, made from transistors, form the hardware of every modern computer.

## Why It Matters

Logic gates are where software meets hardware. The AND gate in a circuit does exactly what the AND operator does in code. Understanding gates explains how a CPU performs calculations at the physical level.

## Core Concepts

| Gate | Behaviour |
|------|-----------|
| AND  | Output 1 only if all inputs are 1 |
| OR   | Output 1 if any input is 1 |
| NOT  | Inverts the input |
| NAND | Opposite of AND |
| NOR  | Opposite of OR |
| XOR  | Output 1 only if inputs differ |

NAND is particularly important — any boolean logic can be built from NAND gates alone. This property is called functional completeness.

## Examples

A half adder adds two bits. It uses one XOR gate (sum) and one AND gate (carry). Two half adders form a full adder. Chain enough full adders and you have an ALU — the arithmetic unit of a CPU.

## Key Takeaways

- Gates are physical implementations of boolean operations.
- They are built from transistors.
- NAND alone is sufficient to build any logic circuit. #flashcard
- Modern CPUs contain billions of these gates.

## Common Mistakes

Thinking of gates as abstract concepts only. They are real physical components with real electrical signals passing through them.

## Related Concepts

- [[04 Boolean Logic]]
- [[09 How a CPU Works]]

## Practice
<!-- Link only: [[04 Practice/Foundation/Logic Gates Practice]] -->

## Resources
