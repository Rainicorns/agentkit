# Project Structure

AgentKit uses a convention-based structure. Files placed in specific locations are automatically discovered and integrated into your agent.

## Basic Structure

```
my-agent/
├── src/
│   ├── agent.ts       # Agent configuration
│   ├── prompt.md      # System prompt (or prompt.ts)
│   └── tools/         # Agent tools (auto-discovered)
│       ├── tool1.ts
│       └── tool2.ts
└── package.json
```

## Entry Point

By default, the agent configuration is in `agent.ts`. You can change this in `package.json`.

```json
{
  "main": "src/agent.ts"
}
```

## Source Directory

All agent code lives in the `src/` directory:

### `src/agent.ts`

The main agent configuration file. Defines model selection, behavior, and other settings.

### `src/prompt.md` or `src/prompt.ts`

The system prompt for your agent.

- Use `prompt.md` for static prompts
- Use `prompt.ts` for dynamic prompts that need to build content programmatically

The framework checks for `prompt.md` first, then falls back to `prompt.ts`.

### `src/tools/`

Tools are auto-discovered from this directory. Each `.ts` file should export a class that extends `AgentTool`.

**Convention:** If a tool file exists in `src/tools/`, it's automatically available to the agent. No manual registration required.

## What Gets Deployed

When you deploy, AgentKit:

1. Bundles your `src/` directory
2. Includes only the tools your agent uses
3. Packages everything as a cloud function (Lambda, etc.)
4. Sets up the necessary infrastructure

The compiled agent is self-contained and ready to run.
