# Getting Started

## Installation

Create a new agent project:

```bash
npx create-agentkit my-agent
cd my-agent
```

This scaffolds a new agent with the recommended structure.

## Project Structure

Your agent project will have this structure:

```
my-agent/
├── src/
│   ├── agent.ts       # Agent configuration
│   ├── prompt.md      # System prompt
│   └── tools/         # Your agent's tools
└── package.json
```

## Local Development

Invoke the agent locally:

```bash
npm run session <initial message>
```

This runs your agent locally. You can invoke it and see responses in real-time.

## Deployment

Deploy your agent to production:

```bash
npm run deploy
```

This bundles your agent and deploys it to AWS Lambda.

## Next Steps

- Learn about [Project Structure](./project-structure.md)
- Understand [Agent Configuration](./agent-configuration.md)
- Create your first [Tool](./tools.md)
- Work with [Prompts](./prompts.md)
