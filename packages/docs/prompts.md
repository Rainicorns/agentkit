# Prompts

Your agent's system prompt can be static or dynamic.

## Static Prompts

Use `src/prompt.md` for static prompts:

```markdown
You are a helpful assistant that answers questions about web development.

Be concise and accurate in your responses.
```

## Dynamic Prompts

Use `src/prompt.ts` for prompts that need to be built dynamically:

```typescript
// src/prompt.ts
export default function buildPrompt(context) {
  return `You are a helpful assistant.

Current date: ${new Date().toISOString()}
User: ${context.user}`
}
```

## How It Works

The framework looks for `prompt.md` first. If not found, it falls back to `prompt.ts`.
