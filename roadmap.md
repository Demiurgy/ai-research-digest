# Roadmap

Ideas for improving the AI Research Digest pipeline.

## v0 — Current version

Current system:

```text
RSS.app Bundle
  → Sim RSS Feed Trigger
  → Sim Agent
  → Condition Filter
  → Telegram Channel
```

What works:

- selected public sources are monitored through RSS
- new feed items are summarized by an AI agent
- low-value items are filtered out
- useful digests are sent to Telegram

## v1 — Better source coverage

Add more source types:

- more X/Twitter accounts
- X/Twitter search queries
- company blogs
- product changelogs
- GitHub releases
- newsletters with RSS
- Substack feeds
- AI tool documentation updates

Possible source groups:

- AI-native product ops
- PM workflows with agents
- marketing/content ops
- generative UI
- internal tools and admin panels
- agent supervision and approval flows

## v2 — Better filtering

Improve signal quality.

Ideas:

- separate `high` and `medium` signal delivery
- send `high` immediately
- collect `medium` into a daily digest
- ignore `low`
- add duplicate detection
- downrank reposts and generic announcements
- detect posts with screenshots, demos, code, prompts, or diagrams

## v3 — Daily and weekly digests

Add summary modes:

- immediate Telegram message for high-signal items
- daily digest grouped by topic
- weekly digest with key patterns and links
- “what changed this week” summary

Example weekly sections:

- Product / PM
- Marketing / content ops
- Admin UI / internal tools
- Generative UI
- Agent workflows
- Interesting tools

## v4 — Personal research memory

Save useful items into a lightweight knowledge base.

Possible destinations:

- Notion
- Obsidian
- Google Sheets
- Airtable
- GitHub markdown archive
- vector database

Useful fields:

- source
- author
- date
- topic
- signal level
- summary
- link
- why it matters
- tags

## v5 — Better agent evaluation

Track whether the agent is useful.

Possible feedback buttons:

- useful
- not useful
- too vague
- already knew this
- wrong topic
- should have been high signal
- should have been filtered out

This feedback can be used to improve:

- source list
- signal rubric
- agent prompt
- filtering logic

## v6 — Multi-channel output

Possible outputs:

- Telegram channel
- Telegram weekly digest
- email summary
- Obsidian note
- GitHub markdown archive
- Slack channel
- dashboard

## v7 — Research assistant mode

Future version:

The system not only summarizes posts, but also detects emerging patterns.

Examples:

- “3 people this week mentioned generative UI replacing dashboards”
- “Retool and CopilotKit are converging on in-app agent control surfaces”
- “Marketing ops examples are more concrete than PM examples this week”
- “New pattern: admin UI as supervision layer, not CRUD surface”

## Open questions

- What signal threshold is strict enough?
- Should medium-signal posts be sent immediately or batched?
- Should the system store all items or only useful ones?
- Should Telegram be the main interface or only a notification layer?
- Should this become a broader personal research OS?
