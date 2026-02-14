---
date: 2026-01-20
tags: [technology, programming, data-oriented-programming]
status: complete
source: Data-Oriented Programming - Yehonathan Sharvit.pdf
title: Data-Oriented Programming
author: Yehonathan Sharvit
publisher: Manning
year: 2022
isbn: 9781617298578
---

"Data-Oriented Programming" presents data-oriented programming (DOP) as a practical way to reduce accidental complexity in information systems such as web applications and services. The central diagnosis is that traditional object-oriented design often mixes code and data inside mutable objects, which increases the number of relationships between entities, makes behavior harder to predict, complicates serialization, and forces explicit synchronization in concurrent environments. DOP attempts to simplify those systems by making data the primary boundary between parts of a program and by designing most logic as stateless functions that transform immutable values.

The book is written as a story that follows developers (Theo, Dave, and Joe) while they refactor and extend a library-management system. That narrative format keeps the discussion grounded in realistic change requests: reshaping data models, implementing queries and mutations, adding concurrency, validating data at boundaries, integrating databases and web services, and debugging production behavior.

At the core of DOP are four language-agnostic principles.

The first principle separates code from data. Data lives in data entities, while code lives in modules that aggregate stateless functions. The book argues that splitting a system into a data side and a code side makes it easier to understand because each entity has a smaller scope and fewer kinds of relations. It also increases flexibility because data and behavior can evolve more independently.

The second principle represents application data with generic data structures, typically maps and arrays (or lists). With generic structures, information is accessible through generic access paths, and a broad set of generic functions becomes available for manipulation, including (de)serialization. This is presented as a deliberate trade: compile-time safety and rigid schemas are reduced in exchange for a data model that can be reshaped as requirements change.

The third principle treats data as immutable. Changes produce new versions of values rather than mutating existing ones. The book emphasizes that immutability makes code behavior more predictable, enables fast equality checks via reference comparisons, and makes read access safe under concurrency. Efficient immutability relies on structural sharing and persistent data structures so that new versions reuse unchanged sub-structures.

The fourth principle separates data schema from data representation. When the shape of data must be enforced, the shape is expressed as data (for example, JSON Schema) and validated at run time. This separation allows selective strictness: some data flows can remain schema-free for speed and exploration, while boundaries and critical invariants can be validated with detailed errors and richer conditions than most static type systems (ranges, regex constraints, optional fields, and composed schemas). The book treats validation as a development aid that can often be disabled in production when appropriate.

Part 1, "Flexibility", starts from the pain points of OOP and builds a DOP architecture around explicit data entities and code modules. Data manipulation is demonstrated through generic access and transformation functions, with the recurring idea that business logic becomes clearer when it reads like a pipeline of transformations on plain data. State management is introduced as a multi-version approach: a mutation is split into a stateless calculation phase that returns a candidate next state, and a stateful commit phase that updates the single authoritative state reference. Structural sharing makes keeping historical versions cheap, which enables undo and "time travel" by switching the state reference back to a previous version.

Concurrency control in this first part is introduced as optimistic concurrency control. Mutations compute next states without locks, and the commit phase reconciles conflicting concurrent mutations when possible, using a merge strategy analogous to Git (fast-forward and three-way merge). The reconciliation leverages structural sharing to compute structural differences efficiently.

Testing follows naturally from the data-first style. Most functions accept and return plain data, so tests become straightforward comparisons between expected and actual values using deep-equality. The book suggests thinking about tests in terms of a tree of function calls: lower-level functions tend to need more test cases because they are reused across more contexts, and mutation tests can focus on the calculation phase (the pure part) rather than on the mechanics of committing state.

Part 2, "Scalability", extends the same principles to larger systems. Basic data validation is positioned as a boundary concern, with guidance to be strict with outbound data and flexible with inbound data, and with practical notes on JSON Schema tooling (for example, Ajv in JavaScript). For multithreaded environments, the book introduces atoms as a lock-free mechanism for managing shared state safely, relying on immutability to keep reads simple and to avoid deadlocks associated with locks.

Persistent data structures receive a focused treatment as the practical foundation that makes immutability scale. The book highlights the role of structural sharing and the internal tree structure (including the common branching-factor approach) that keeps updates and copies efficient even for very large collections.

Database operations and web services are presented as places where DOP fits naturally because external boundaries already speak in data. Database result sets become lists of maps; field names become first-class strings; and generic functions can rename keys, group rows, and build derived shapes without creating a large hierarchy of domain objects. Web service logic is described as "building the insides like the outsides": internal components communicate via the same kind of immutable request/response maps that appear on the wire, which keeps coupling low and supports a clear data flow through parsing, validation, enrichment, and serialization.

Part 3, "Maintainability", focuses on techniques that matter in long-lived codebases and teams. Advanced data validation extends JSON Schema usage inside the system, particularly for function arguments and return values, with an emphasis that such checks are development-time aids. The book also shows how schemas can be used to generate diagrams and schema-based unit tests.

Polymorphism is addressed without returning to objects. The book introduces multimethods: a dispatch function computes a dispatch value from the call arguments, and separate method implementations are registered for dispatch values. Single dispatch can mimic class-based polymorphism by dispatching on a type field, while multiple dispatch and dynamic dispatch allow behavior selection based on multiple arguments or other run-time properties.

Advanced data manipulation is framed as a readability and naming discipline. When low-level transformations (especially reduce) leak into business logic, the code becomes harder to scan. The book recommends building small, well-named generic helpers (such as update, flatMap, unwind, or count-by helpers) so that business logic reads in terms of intent while the mechanical details remain localized.

Debugging is presented through the lens of reproducibility. In modules that operate only on immutable data, behavior is deterministic: the same arguments lead to the same return values. That makes it possible to capture the context in which a function ran (its arguments, serialized) and replay the scenario in a REPL or unit test. Reproducibility is described as depending on two conditions: immutability and ease of (de)serialization. The approach enables short feedback loops and turns production incidents into test cases.

Across the book, DOP is not presented as free of trade-offs. Data transparency weakens encapsulation and removes automatic constraints on which code may access which data. Generic data structures reduce compile-time guarantees and can require explicit casting in some statically typed languages. Immutability can impose a small performance cost and may require third-party persistent data structure libraries with conversion overhead at integration boundaries. Schema separation provides flexibility but also relies on discipline to apply validation where it matters.

The overall message is that much of the complexity in everyday application code is not inherent to the business domain. It emerges from how data and behavior are packaged and from how state is mutated. By separating code from data, representing data with generic structures, embracing immutability, and using explicit schemas where needed, systems tend to become easier to change, easier to test, and easier to reason about under concurrency.
