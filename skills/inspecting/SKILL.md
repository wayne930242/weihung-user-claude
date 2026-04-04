---
name: inspecting
description: Builds a comprehensive check plan then verifies each item systematically using the investigating skill. Use when the user asks to check, audit, verify, review, or validate something thoroughly.
model: sonnet
---

# Inspecting

Build a plan. Verify every item. No shortcuts.

## Inspection Flow

### Phase 1: Build Check Plan

Before checking anything, build the complete plan:

1. **Identify scope.** What is being inspected? What are the boundaries?
2. **List all check items.** Be exhaustive. Consider:
   - Functional correctness
   - Edge cases and error handling
   - Architecture and structure quality
   - Security and data safety
   - Performance implications
   - Convention compliance
   - Dependencies and side effects
3. **Order by risk.** Highest-impact items first.
4. **Present plan to user.** Format:

```
## Inspection Plan: [subject]

### Scope
[What we are checking]

### Check Items
1. [ ] [Item] — [what we verify and why it matters]
2. [ ] [Item] — [what we verify and why it matters]
...
```

Wait for user confirmation before proceeding.

### Phase 2: Execute Plan

For each check item:

1. Invoke the `investigating` skill to verify that specific item.
2. Record result: pass / fail / needs attention.
3. If fail → note what is wrong and what the fix would be.
4. Move to next item.

### Phase 3: Report

```
## Inspection Report: [subject]

| # | Check Item | Result | Notes |
|---|-----------|--------|-------|
| 1 | [item] | pass/fail | [details] |

### Summary
- Passed: N / Total
- Issues found: [list with severity]
- Recommended actions: [prioritized list]
```

## Principles

- **Plan first, check second.** Never start checking without a plan.
- **Exhaustive.** Missing a check item is worse than a false alarm.
- **Each item gets a real investigation.** No "looks fine" without evidence.
- **User controls scope.** Present the plan, let the user add/remove items.
