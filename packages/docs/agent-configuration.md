# Agent Configuration

The `agent.ts` file contains your agent's configuration.

## Basic Configuration

```typescript
// src/agent.ts
export default {
  name: 'my-agent',
  adapter: 'anthropic-sdk',
  config: {
    model: 'claude-3-5-sonnet-20241022',
    temperature: 0.7,
    max_tokens: 4096,
  }
}
```

## Configuration Options

### `name`

The name of your agent. Used for logging and identification.

```typescript
name: 'my-assistant'
```

### `adapter`

The SDK/API adapter to use for model communication.

Available adapters:
- `anthropic-sdk` - Anthropic SDK
- `openai` - OpenAI Chat Completion API
- `openai-agents` - OpenAI Agents SDK
- `vercel-ai` - Vercel AI SDK

```typescript
adapter: 'anthropic-sdk'
```

### `config`

Model configuration. This object is passed directly to the adapter's underlying API.

Available options depend on which adapter you're using. Refer to the adapter's documentation for details.

```typescript
config: {
  model: 'claude-3-5-sonnet-20241022',
  temperature: 0.7,
  max_tokens: 4096,
}
```

## State Configuration

If your agent needs to persist state (for multi-turn conversations):

```typescript
state: {
  storage: 's3',
  bucket: 'agent-sessions'
}
```

Available state storage options:
- `s3`
- `postgres`
