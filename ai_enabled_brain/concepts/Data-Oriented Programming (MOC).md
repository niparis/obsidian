---
date: 2026-01-20
tags: [moc, technology, programming, data-oriented-programming]
status: draft
---

Data-Oriented Programming is a small hub for notes related to Yehonathan Sharvit's book and to the broader DOP paradigm.

## Core Note

- [[Data-Oriented Programming - Yehonathan Sharvit (Summary)]]

## Key Ideas

- Principle 1: Separate code from data
- Principle 2: Represent data with generic data structures
- Principle 3: Data is immutable
- Principle 4: Separate data schema from data representation

## Techniques And Patterns

- Stateless functions and explicit data flow
- Multi-version state (calculation phase vs commit phase)
- Structural sharing and persistent data structures
- Optimistic concurrency control (reconciliation / merge)
- Atoms as a lock-free shared-state primitive
- Schema-at-the-boundary validation (JSON Schema)
- Multimethods for polymorphism over maps
- Debugging via context capture and replay (REPL / unit tests)

## Practical Notes (To Be Written)

- When DOP fits well (web APIs, information systems)
- Costs / trade-offs (less encapsulation, runtime validation, library needs)
- Team conventions (naming, helper functions, where schemas live)

## Related Topics

- [[Functional Programming]]
- [[Object-Oriented Programming]]
- [[Immutability]]
- [[Persistent Data Structures]]
- [[JSON Schema]]
- [[Optimistic Concurrency Control]]
- [[Multimethods]]

## Follow-ups

- Extract examples into small, reusable patterns (update, flatMap, unwind)
- Add links to project notes where DOP techniques are applied
