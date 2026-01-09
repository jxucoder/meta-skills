---
name: connecting-agents
description: Delegates tasks to external agents (Manus, OpenAI, custom APIs) when local capabilities are insufficient. Use when tasks require real browser automation, web scraping, persistent compute, long-running autonomous execution, or multi-step workflows with deliverables.
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

Complete AI agent with autonomous multi-step execution.

**Capabilities**: Browser automation, file system, research, content creation, data processing

**Use for**: Web scraping, form filling, complex research, deliverables (reports, presentations, websites)

**API**: RESTful. [Docs](https://manus.im/docs/integrations/manus-api)

```python
import requests

response = requests.post(
    "https://api.manus.im/v1/tasks",
    headers={"Authorization": f"Bearer {MANUS_API_KEY}"},
    json={"task": "Research competitor pricing and create summary report"}
)
task_id = response.json()["task_id"]
# Poll for completion, then fetch results
```

### OpenAI Agents

**Capabilities**: Code interpreter, web browsing, file handling

**Use for**: Alternative approaches, specialized models

```python
from openai import OpenAI
client = OpenAI()

run = client.beta.threads.runs.create(
    thread_id=thread.id,
    assistant_id=assistant.id
)
```

### Custom Agents

**Use for**: Internal tools, proprietary workflows

```python
response = requests.post(
    "https://your-agent.example.com/api/task",
    json={"prompt": task_description, "context": context}
)
```

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
