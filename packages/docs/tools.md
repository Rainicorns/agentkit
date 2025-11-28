# Tools

Tools are automatically discovered from the `src/tools/` directory. Each `.ts` file represents one tool.

## Creating a Tool

Create a file in `src/tools/` and extend the `AgentTool` class:

```typescript
// src/tools/web-search.ts
import { AgentTool } from '@agentkit/runtime'
import { z } from 'zod'

export class WebSearchTool extends AgentTool {
  name = 'web_search'
  description = 'Search the web for information'

  parameters = z.object({
    query: z.string().describe('Search query')
  })

  async execute(params: { query: string }) {
    // Your tool implementation
    const results = await fetch(`https://api.example.com/search?q=${params.query}`)
    return results.json()
  }
}
```

## Auto-Discovery

Tools are automatically discovered and registered with your agent. If the file exists in `src/tools/`, the agent can use it.

No manual registration required.

## Tool Structure

### `name`

The name of the tool. Used by the agent to invoke it.

### `description`

What the tool does. The agent uses this to decide when to use the tool.

### `parameters`

Zod schema describing the tool's parameters.

### `execute()`

The function that runs when the agent invokes the tool. Returns the result to the agent.
