---
title: Boolean Logic
status: Complete
tags: [topic/foundation, type/concept]
created: 2025-06-30
---

# Boolean Logic

## Overview

Boolean logic is a system where every value is either True or False. Developed by George Boole in 1854, it forms the mathematical foundation of all digital computing.

## Why It Matters

Every decision a computer makes is a boolean operation. Every `if` statement, every comparison, every conditional branch traces back to AND, OR, and NOT.

## Core Concepts

**AND** — True only if both inputs are True.

| A | B | A AND B |
|---|---|---------|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

**OR** — True if at least one input is True.

| A | B | A OR B |
|---|---|--------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

**NOT** — Flips the input.

| A | NOT A |
|---|-------|
| 0 | 1 |
| 1 | 0 |

**XOR** — True only if exactly one input is True (not both).

## Examples

In code: `if (age >= 18 AND hasID == true)` — both conditions must be True for the block to run.

In code: `if (isWeekend OR isHoliday)` — either condition being True is enough.

## Key Takeaways

- Boolean values are True (1) or False (0). #flashcard
- AND, OR, NOT are the three fundamental operations.
- All complex computer logic is built from combinations of these.

## Common Mistakes

Confusing OR with XOR. Regular OR is True when either or both inputs are True. XOR is only True when exactly one is True.

## Related Concepts

- [[05 Logic Gates]]
- [[02 Binary Numbers]]

## Practice
<!-- Link only: [[04 Practice/Foundation/Boolean Logic Practice]] -->

## Resources
