---
description: Architecture quality gates and refactoring triggers
---

# Clean Architecture

## Refactoring Triggers

Act on these immediately when spotted:

- God object: class/module with 3+ unrelated responsibilities - split
- Circular dependency: A imports B imports A - extract shared interface
- Wrong abstraction level: UI logic in data layer or vice versa - move
- Leaky abstraction: internal details exposed in public API - encapsulate
- Dead code: unreachable functions or unused exports - delete

## Structure Rules

- One export per file for major components. Barrel files (index.ts) only at module boundaries.
- Dependency direction: handlers -> services -> repositories. Never reverse.
- Config at the edges. No hardcoded values in business logic.
- Error types per domain. No generic "Error" or string throws.
