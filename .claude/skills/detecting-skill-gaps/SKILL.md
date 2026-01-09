---
name: detecting-skill-gaps
description: Identifies missing capabilities that warrant new skills. Analyzes repeated friction patterns, failed tasks, and user workarounds to recommend skill creation. Use when discovering-skills finds nothing suitable.
allowed-tools: Read, Glob, WebSearch
---

# Detecting Skill Gaps

Identify when a new skill should be created.

## Signals of a Gap

1. **Repeated friction** - Same workaround applied multiple times
2. **Failed searches** - discovering-skills found nothing suitable
3. **Manual patterns** - User repeatedly provides the same instructions
4. **Capability boundaries** - Task requires approach Claude struggles with

## Detection Process

1. Observe task execution patterns
2. Note where friction occurs
3. Classify the friction type
4. Determine if skill would address it
5. Recommend creation or external delegation

## Friction Classification

| Type | Example | Resolution |
|------|---------|------------|
| Knowledge | "How do I configure X?" | Documentation skill |
| Process | Multi-step workflow repeated | Automation skill |
| Convention | Same style corrections | Standards skill |
| Integration | External service patterns | Connector skill |
| Capability | Beyond Claude's abilities | connecting-agents |

## When to Recommend New Skill

**Create skill when:**
- Pattern appears 3+ times
- Friction is addressable via instructions
- Benefit exceeds creation effort
- No existing skill is adaptable

**Don't create when:**
- One-off task
- External capability required (use connecting-agents)
- Existing skill can be adapted (use adapting-skills)

## Gap Report Format

```
Gap Identified: [short name]
Friction Type: [knowledge/process/convention/integration/capability]
Occurrences: [count or "recurring"]
Impact: [time lost, errors caused, user frustration]
Recommended Action: [create skill / adapt X / delegate to Y]
Suggested Skill Name: [if creating]
```

## Reference Documentation

- **Skill authoring**: https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices

## Integration

- Gap addressable locally → draft skill specification
- Gap requires external capability → suggest connecting-agents
- Similar skill exists → suggest adapting-skills
- Multiple related gaps → suggest consolidated skill
