---
title: Complexity Overview
status: Complete
tags: [topic/foundation, type/concept]
created: 2025-06-30
---

# Complexity Overview

## Overview

Complexity measures how the resources an algorithm uses — usually time or memory — grow as the input size grows. It answers: if I double the amount of data, how much longer does this take?

This is a brief introduction. Big-O notation is covered fully in Phase 04 Algorithms.

## Key Points

- **Time complexity** measures how many steps an algorithm takes.
- **Space complexity** measures how much memory it uses.
- Input size is written as `n`.
- Big-O notation describes the worst-case growth rate.
- O(1) is constant — does not grow with input size.
- O(n) is linear — doubles when input doubles.
- O(n²) is quadratic — quadruples when input doubles.

## Example

Searching a list by checking every item is O(n) — double the list, double the time. Binary search is O(log n) — doubling the list adds only one extra step.

## Related Concepts

- [[06 What is an Algorithm]]

## Resources
