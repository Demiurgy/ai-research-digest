# Workflow

Current workflow implemented in Sim.

## Pipeline

```text
RSS.app Bundle
  → Sim RSS Feed Trigger
  → Sim Agent
  → Sim Condition
  → Telegram Send Message
```

## Step 1: RSS.app Bundle

RSS.app is used to convert public X/Twitter profiles and RSS sources into feeds.

Multiple feeds are combined into one RSS.app Bundle.

The private Bundle URL is used in Sim RSS Feed Trigger.

Do not commit the private Bundle URL to this repository.

## Step 2: Sim RSS Feed Trigger

The Sim workflow starts when a new RSS item appears in the Bundle feed.

Manual runs may use mock data. Real data appears only when the deployed workflow receives a new RSS item.

## Step 3: Sim Agent

The Agent receives the RSS item and produces a short Russian digest.

The prompt is stored in:

```text
agent-prompt.md
```

## Step 4: Condition Filter

The Condition block checks whether the Agent output contains:

```text
Открывать ссылку: yes
```

Only items marked as worth opening are sent to Telegram.

Low-value items are ignored.

## Step 5: Telegram Send Message

Telegram receives the Agent output.

Required runtime secrets:

- Telegram bot token
- Telegram channel chat_id

These values must be stored only inside Sim or local private notes.

They must not be committed to git.
