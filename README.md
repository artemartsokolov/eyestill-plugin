# EyeStill for Claude

Read web pages, public-domain books and Claude's own answers faster: one word at a time in a fixed spot, right
in the chat. You set the speed, and Claude knows where you are, so it can explain the passage, recap, quiz you
or continue later from the same word. (The words scroll past on a rotating cylinder, like a slot-machine reel.)

- `/eyestill https://…` — read a web page
- `/eyestill Moby Dick, chapter 30` — a public-domain book from Project Gutenberg, from a chapter
- `/eyestill why is the sky blue?` — the answer, written straight into the reader
- `/eyestill` — your last answer in the reader

The plugin adds the EyeStill connector (`https://eyestill.com/mcp`, no account) and a skill with these rules.

Docs: https://eyestill.com/apps · Privacy: https://eyestill.com/privacy · Terms: https://eyestill.com/terms ·
Support: support@eyestill.com

## Install

In Claude Code:

```
/plugin marketplace add artemartsokolov/eyestill-plugin
/plugin install eyestill@eyestill
```

In the Claude apps, find EyeStill in the directory, or add the connector `https://eyestill.com/mcp` under
Settings → Connectors.
