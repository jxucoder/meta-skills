---
name: optimizing-context
description: Audits and optimizes context, memory, and skill use for projects. Reviews CLAUDE.md files, .claude/rules/, and skill configurations for efficiency. Use when context feels bloated, skills aren't triggering correctly, or memory needs organization.
allowed-tools: Read, Glob, WebFetch, Write
---

# Optimizing Context

Audit and optimize how context, memory, and skills are configured.

## When to Use

- Context window feels cluttered or inefficient
- Skills aren't triggering as expected
- CLAUDE.md or rules need review
- Starting a new project and setting up memory
- Periodic maintenance of existing configurations

## Audit Process

1. **Inventory** - List all memory files and skills
2. **Review** - Check each for conciseness and relevance
3. **Identify** - Find redundancy, verbosity, or gaps
4. **Recommend** - Suggest specific optimizations
5. **Implement** - Apply changes with user approval

## What to Check

| Component | Location | Look For |
|-----------|----------|----------|
| Project memory | `CLAUDE.md` | Verbosity, outdated info, missing essentials |
| Local memory | `CLAUDE.local.md` | Personal prefs that should be global |
| Rules | `.claude/rules/*.md` | Overlap, poor organization, missing globs |
| Skills | `.claude/skills/*/SKILL.md` | Unclear descriptions, excessive content |
| User memory | `~/.claude/CLAUDE.md` | Project-specific content that doesn't belong |

## Key Principles

- **Concise is key** - Every token competes for context space
- **Progressive disclosure** - Link to details, don't inline everything
- **One level deep** - Avoid nested file references
- **Specific descriptions** - Skills need clear triggers in descriptions

## Reference Documentation

For detailed guidance, visit these pages:

- **Memory management**: https://code.claude.com/docs/en/memory
- **Skill authoring**: https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices
- **Claude Code best practices**: https://www.anthropic.com/engineering/claude-code-best-practices

## Audit Report Format

```
Context Audit: [project name]
Date: [date]

Memory Files:
- [file]: [status] - [notes]

Skills:
- [skill]: [status] - [notes]

Issues Found:
1. [issue] → [recommendation]

Optimizations Applied:
- [change made]
```
