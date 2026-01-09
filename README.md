# Meta-Skills

> A meta-skill enables an agent to manage its own capabilities and extend them through other agents.

## What Are Meta-Skills?

Meta-skills give agents **agency over their own skill ecosystem**. Unlike regular skills that perform tasks, meta-skills enable agents to:

- Recognize capability gaps
- Find and adapt existing skills
- Combine skills for complex tasks
- Delegate to external agents

## The Skills

| Skill | Type | Purpose |
|-------|------|---------|
| `discovering-skills` | Introspective | Find existing skills before building new ones |
| `adapting-skills` | Introspective | Modify skills for new contexts |
| `connecting-agents` | Connective | Delegate to external agents (Manus, etc.) |

### Two Dimensions

**Introspective**: Agent reasons about its own skill ecosystem

**Connective**: Agent delegates to external agents when needed

### Planned Skills

- `detecting-skill-gaps` - Recognize when a skill would help but doesn't exist
- `fusing-skills` - Combine multiple skills for complex tasks

## Installation

Copy to your Claude skills directory:

```bash
# Personal (applies to all projects)
cp -r .claude/skills/* ~/.claude/skills/

# Or keep in project (applies to this repo only)
# Skills are already in .claude/skills/
```

## Usage

These skills activate automatically when relevant. Examples:

**Discovery**
> User: "I need to work with PDFs"  
> Claude: Searches for existing PDF skills before attempting the task

**Adaptation**
> User: "This skill is close but uses the wrong framework"  
> Claude: Forks the skill and adapts it for your context

**Delegation**
> User: "Fill out this web form with the data"  
> Claude: "This requires browser automation. Delegating to Manus..."

## Philosophy

Most "meta-skills" are just documentation repackaged. These are different:

- **Skill utilities** help humans manage skills
- **Meta-skills** give agents agency over their capabilities

The goal is agents that improve how they acquire and use capabilities, not just use them.

## License

MIT
