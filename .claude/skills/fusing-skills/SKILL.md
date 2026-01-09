---
name: fusing-skills
description: Combines multiple skills to handle complex tasks requiring diverse capabilities. Orchestrates skill activation order, manages data flow between skills, and resolves conflicts. Use when a task spans multiple domains.
---

# Fusing Skills

Combine skills when a task requires capabilities from multiple domains.

## When to Fuse

- Task explicitly spans domains (e.g., "extract data from PDF and create Excel chart")
- Single skill insufficient but multiple together would work
- User requests integration of separate workflows

## Fusion Patterns

### Sequential
Skills execute in order, output of one feeds the next.

```
Task: PDF → data extraction → Excel chart
Flow: pdf-processing → xlsx-processing
```

### Parallel
Skills execute independently, results combined.

```
Task: Analyze code quality and security
Flow: code-review + security-scan → combined report
```

### Conditional
Skill selection based on intermediate results.

```
Task: Process document (format unknown)
Flow: detect format → route to appropriate skill
```

## Execution

1. Identify required capabilities
2. Map to available skills
3. Determine execution pattern
4. Manage data handoff between skills
5. Combine outputs coherently

## Conflict Resolution

When skills have conflicting instructions:
- More specific skill takes precedence
- User's explicit preferences override both
- Ask for clarification if ambiguous
