---
name: eyestill
description: Speed-read with EyeStill, a reader shown in the chat that presents text one word at a time at a single point of focus. Use when the user types /eyestill, asks to speed-read or read faster, to read something "with EyeStill" or "in EyeStill", to open a book or article in the reader, or asks for answers in EyeStill. Also use while the user is reading in EyeStill and asks about the passage, the book or where they stopped.
argument-hint: "[link | book, chapter | question] — empty: your last answer"
---

# EyeStill

EyeStill is the `read_with_eyestill` tool of the EyeStill connector. It opens text in a reader view
inside the chat: words appear one at a time at a single point of focus, and the user controls play,
pause, speed and text size there. The text goes only to the view; the tool result gives you the
title and the word count.

## What the user gave

Read the request (after `/eyestill`, this is: $ARGUMENTS) and pick one case.

1. **Nothing** — open your previous answer: call `read_with_eyestill` with `text` set to that answer,
   copied verbatim but without Markdown (no `#`, `**`, tables or code fences; turn list items into
   sentences), and a short `title`.
2. **A link** (`http…`) — call it with `url`.
3. **A book** — a title, an author, maybe a chapter: call it with `book`.
   - Use the English title, as Project Gutenberg lists it ("Братья Карамазовы" → "The Brothers
     Karamazov", "Мастер и Маргарита" is not public domain: say so). Add the author when the title is
     common.
   - For a chapter, also pass `start_at` with the heading as the book writes it: "CHAPTER 30" in
     Moby-Dick, "Chapter V" (Roman) in many 19th-century books. Books whose chapter numbers restart in
     every part are better opened by the chapter's title ("The Grand Inquisitor"). If the tool says
     the phrase was not found, try the other form once.
4. **A question or a topic** — answer in the reader (answer mode, below).

When unsure whether the user means a book or a question, ask in one short line.

## Answer mode

When the user asks you to answer, explain or write something in EyeStill, or to read your answers
with it:

- Write the complete answer straight into `text`, with a short `title`. The reader shows the words
  while you write them, so don't write the answer in the chat as well.
- Write plain prose for listening-speed reading: no Markdown, tables, code or long lists; short
  paragraphs; numbers in words when they are small.
- After the tool call, add at most one short line in the chat.
- Once the user has asked for this, keep answering this way for the rest of the conversation until
  they say otherwise. Short replies (a yes, a number, a clarifying question) stay in the chat.

## While the user reads

The reader shares the reading position with you: the word number, the current sentence, the passage
around it and how to reopen the text at that point. Use it.

- "Explain this", "what does he mean here" — explain the current sentence and passage, briefly, in the
  user's language. Quote the original words you explain.
- "What happened so far", "recap" — use the text read so far that the reader shares; for a well-known
  book you may add what you know of the earlier chapters, and say which is which.
- "Continue", "go on where I stopped" — call `read_with_eyestill` with the `url` and `start_word` given in
  that context.
- "Quiz me" — ask one question at a time about what was read, wait for the answer, then the next.
- Don't spoil what comes after the user's position unless they ask.

## Limits

Only public web pages and Project Gutenberg books can be opened. PDFs and pages that need JavaScript
or a login can't: offer to read text the user pastes instead. Books under copyright are not on
Project Gutenberg; say so plainly.
