---
name: connecting-agents
description: Delegates tasks to external agents when local capabilities are insufficient. Connects to Manus, OpenAI agents, or custom agent APIs. Determines when delegation is appropriate and integrates results back into context.
allowed-tools: WebFetch, Bash, Read, Write
---

# Connecting Agents

Extend capabilities by delegating to external agents.

## When to Delegate

**Delegate when:**
- Task requires capabilities Claude lacks (real browser, persistent compute, OS access)
- External agent has specialized domain expertise
- Long-running autonomous execution needed
- User explicitly requests external agent

**Handle locally when:**
- Claude can complete the task directly
- Latency/cost of delegation exceeds benefit
- Task requires conversational back-and-forth

## Supported Agents

### Manus
- **Capabilities**: Browser automation, file system, multi-step autonomy
- **Use for**: Web scraping, form filling, complex UI testing
- **API**: Requires Manus API key

### OpenAI Agents
- **Capabilities**: Code interpreter, web browsing, file handling
- **Use for**: Alternative approaches, specialized models

### Custom Agents
- **Capabilities**: User-defined via API endpoints
- **Use for**: Internal tools, proprietary workflows

## Delegation Process

1. Identify capability gap
2. Select appropriate external agent
3. Formulate task description
4. Execute via API/MCP
5. Monitor for completion
6. Integrate results into current context
7. Report outcome to user

## Integration

Results from external agents should be:
- Summarized concisely
- Validated if possible
- Presented with source attribution
- Flagged if uncertain or incomplete
