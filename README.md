# EyeStill for Claude

Speed-read in the chat: web pages, public-domain books and Claude's own answers, one word at a time at a
single point of focus, on a 3D drum. While you read, Claude knows where you are and can explain the passage,
recap, quiz you or continue later from the same word.

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
