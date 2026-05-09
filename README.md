# AI Research Digest

Personal AI research digest pipeline.

The system monitors selected X/Twitter accounts and RSS sources, summarizes useful signals with an AI agent, filters low-value posts, and sends concise digests to Telegram.

## Goal

Avoid scrolling social feeds manually.

Instead, receive short Telegram summaries only when a source posts something potentially useful about:

- AI-native product work
- PM workflows with agents
- AI marketing/content ops
- internal tools
- admin panels
- generative UI
- agentic workflows

## Current architecture

```text
RSS.app Bundle
        ↓
Sim RSS Feed Trigger
        ↓
Sim Agent
        ↓
Condition Filter
        ↓
Telegram Channel

