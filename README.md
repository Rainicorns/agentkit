# AgentKit

**The framework for deploying LLM agents with amazing DX.**

## Motivation

Building and deploying LLM agents today requires stitching together libraries, cloud services, bundlers, and infrastructure. You write agent code, but then you're stuck figuring out how to actually run it in production.

**AgentKit makes agent deployment as easy as web deployment.**

Inspired by the DX of Vercel, SvelteKit, and Heroku - tools that made it trivially easy to go from code to production - AgentKit does the same for LLM agents.

## Goals

**Primary goal:** Make agent deployment DX as awesome as possible.

This means:
- Fast to start
- Convention-based structure
- Local dev that works instantly
- One-command deploy
- Minimal configuration, smart defaults

Think: the Vercel of agents.

## Project Structure

AgentKit is organized as a pnpm monorepo:

```
agentkit/
├── packages/
│   ├── agentkit/           # Main framework (runtime + CLI)
│   ├── create-agentkit/    # Project scaffolding tool
│   ├── docs/               # Documentation site
│   └── www/                # Marketing website
│
└── examples/               # Example agents
```

## Status

🚧 **Early Development** - This framework is in active design and development.

## License

MIT
