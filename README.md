# AI Research Digest

A personal AI research digest pipeline.

The system monitors selected X/Twitter accounts and RSS sources, summarizes useful signals with an AI agent, filters low-value posts, and sends concise digests to Telegram.

## Why

The goal is to avoid manually scrolling social feeds.

Instead of reading the full timeline, the system delivers short Telegram summaries only when a source posts something potentially useful about:

- AI-native product work
- PM workflows with agents
- AI marketing and content operations
- internal tools
- admin panels and back-office workflows
- generative UI
- agentic workflows
- supervision and approval layers

## Architecture

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

| Component | Role |
|---|---|
| RSS.app | Converts public X/Twitter profiles and RSS sources into RSS feeds |
| RSS.app Bundle | Combines multiple feeds into one feed |
| Sim | Runs the workflow and agent logic |
| Sim Agent | Summarizes and classifies each incoming item |
| Sim Condition | Filters low-value items |
| Telegram Bot | Sends the final digest to a Telegram channel |

## Repository contents

| File | Description |
|---|---|
| `sources.md` | Public sources monitored by the digest |
| `agent-prompt.md` | Prompt used by the Sim Agent |
| `workflow.md` | Current workflow design |
| `setup.md` | Setup instructions |
| `signal-rubric.md` | Rules for deciding whether an item is worth attention |
| `example-output.md` | Example Telegram digest message |

## Signal criteria

The digest prioritizes posts with practical signals:

- real workflow
- concrete product/admin UI pattern
- agent or automation pipeline
- before/after process change
- screenshots, demos, examples, tools, prompts, architecture
- PM/product ops, marketing ops, internal tools, back-office, admin panels, generative UI

The digest downranks:

- vague opinions
- hype
- generic AI takes
- motivational content
- announcements without operational substance

## Safety

Secrets are not stored in this repository.

Do not commit:

- Telegram bot token
- Telegram chat_id
- API keys
- private RSS.app feed URLs
- local credentials
