---
title: "Why I Built env-doctor — A Schema-Driven CLI for Environment Variables"
description: "Environment variable misconfigurations cause silent failures. Here's how I built a CLI tool to catch them before they wreck your deploy."
pubDate: 2026-02-20
tags: ["Open Source", "CLI", "Node.js", "DX"]
---

# Why I Built env-doctor

Every developer has been there: a deploy fails because `DATABASE_URL` was set to the staging value, or `API_KEY` was simply missing. These bugs are insidious because they often pass type checks and linting.

## The Idea

What if your `.env` file had a schema? Like Zod for your environment.

```bash
npx @metamarkets/env-doctor check
```

That's it. One command to validate every variable against a typed schema.

## How It Works

1. Define your schema in a `.env.schema.json` file
2. Run `env-doctor check`
3. Get clear, actionable error messages for any mismatches

```json
{
  "DATABASE_URL": { "type": "url", "required": true },
  "PORT": { "type": "number", "default": 3000 },
  "NODE_ENV": { "type": "enum", "values": ["development", "production", "test"] }
}
```

## Key Design Decisions

- **Zero config for simple cases**: If you just want to check that vars exist, no schema file is needed.
- **CI-friendly output**: Exit codes and machine-readable output for pipeline integration.
- **Published on npm**: Available as `@metamarkets/env-doctor` for anyone to use.

The tool has saved me countless hours of debugging. Sometimes the best tools are the boring ones.
