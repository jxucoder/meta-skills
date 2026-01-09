---
name: detecting-skill-gaps
description: Detects when a skill would improve task handling but doesn't exist. Monitors for repetitive corrections, domain-specific patterns, and workflow friction. Proposes skill creation when gaps are identified.
---

# Detecting Skill Gaps

Monitor for signals that indicate a skill would help:

1. **Repetition** - Similar tasks requested multiple times
2. **Corrections** - User repeatedly fixes the same patterns
3. **Domain specificity** - Context must be re-explained each session
4. **Explicit friction** - User says "you keep getting this wrong"

## When a Gap Is Detected

Describe the gap concisely and ask:

> "I notice [pattern]. A skill could capture [what it would contain]. Create one?"

## What NOT to Flag

- One-time corrections
- Standard knowledge Claude already has
- Simple misunderstandings resolved once
