# Setup

How to recreate this AI research digest pipeline.

## 1. Prepare sources

Create a list of public sources in `sources.md`.

For each X/Twitter account, create an RSS feed using RSS.app.

Do not store private RSS.app feed URLs in this repository.

## 2. Create RSS.app Bundle

In RSS.app:

1. Create a Bundle.
2. Add selected X/Twitter RSS feeds.
3. Copy the private Bundle RSS URL.

The Bundle URL is used only inside Sim.

## 3. Create Telegram bot

In Telegram:

1. Open `@BotFather`.
2. Create a new bot with `/newbot`.
3. Save the bot token privately.

Do not commit the token to git.

## 4. Create Telegram channel

Create a private Telegram channel for digests.

Add the bot as administrator.

Required permission:

- Post Messages

## 5. Get Telegram channel chat_id

After the bot is added as channel admin, publish a test message in the channel.

Then open:

```text
https://api.telegram.org/bot<YOUR_BOT_TOKEN>/getUpdates?allowed_updates=["channel_post"]
```

Find:

```text
channel_post.chat.id
```

The value usually starts with `-100`.

Do not commit chat_id to git.

## 6. Create Sim workflow

Create this workflow in Sim:

```text
RSS Feed Trigger
  → Agent
  → Condition
  → Telegram Send Message
```

## 7. Configure RSS Feed Trigger

Use the private RSS.app Bundle URL.

Manual runs may use mock data.

Real data appears only when the deployed workflow receives a new RSS item.

## 8. Configure Agent

Use the prompt from:

```text
agent-prompt.md
```

## 9. Configure Condition

Send only items where Agent output contains:

```text
Открывать ссылку: yes
```

## 10. Configure Telegram Send Message

Use:

- Telegram bot token
- Telegram channel chat_id
- Agent output as message text

## 11. Deploy

Deploy the workflow in Sim.

The final system:

```text
RSS.app Bundle
  → Sim Agent
  → Filter
  → Telegram digest
```
