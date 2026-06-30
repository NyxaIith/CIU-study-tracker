---
title: How Code Becomes a Program
status: Complete
tags: [topic/foundation, type/concept]
created: 2025-06-30
---

# How Code Becomes a Program

## Overview

Source code is human-readable text. A CPU can only execute binary machine code. The process of turning one into the other is either compilation or interpretation.

## Why It Matters

This explains why some languages are fast and others flexible, why errors happen at different stages, and what compilers and interpreters actually do.

## Core Concepts

**Compilation**
The entire source code is translated into machine code before running. The result is an executable file. Languages: C, C++, Rust, Go.

Source code → Compiler → Machine code → Execution

Advantages: Fast execution, errors caught before running.
Disadvantage: Must compile separately for each target platform.

**Interpretation**
Source code is read and executed line by line at runtime. No separate compilation step. Languages: Python, Ruby.

Source code → Interpreter → Execution (line by line)

Advantages: Portable, flexible, easier to test interactively.
Disadvantage: Slower than compiled code.

**JIT Compilation (Hybrid)**
Source code compiles to an intermediate bytecode, then a Just-In-Time compiler translates it to machine code at runtime. Languages: Java, C#, modern JavaScript.

**Linking and Loading**
Large programs are split into multiple compiled files. The linker combines them into one executable. The loader places the program into RAM when it runs.

## Examples

`python3 script.py` — launches the interpreter, which reads and executes the file directly.

`gcc program.c -o program` — compiles C code into a binary the OS can run.

## Key Takeaways

- Compiled code is translated before running — fast but less portable. #flashcard
- Interpreted code is translated at runtime — portable but slower. #flashcard
- JIT compilation is a hybrid approach that can approach compiled performance.
- All code eventually becomes machine code the CPU executes.

## Common Mistakes

Thinking interpreted languages cannot be fast. Modern JIT compilers can reach near-compiled performance for many workloads.

## Related Concepts

- [[09 How a CPU Works]]
- [[11 What is an Operating System]]

## Practice
<!-- Link only: [[04 Practice/Foundation/Code Execution Practice]] -->

## Resources
