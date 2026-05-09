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
```

## Components
| Component      | Role                                                       |
| -------------- | ---------------------------------------------------------- |
| RSS.app        | Converts X/Twitter profiles and RSS sources into feed URLs |
| RSS.app Bundle | Combines multiple sources into one RSS feed                |
| Sim            | Runs the workflow and agent logic                          |
| Sim Agent      | Summarizes and classifies each incoming item               |
| Sim Condition  | Sends only useful items further                            |
| Telegram Bot   | Posts the final digest to a private Telegram channel       |


## Safety

Secrets are not stored in this repository.
