---
name: pulsar-reflect
description: Summarize recent commits grouped by day, one concise bullet per commit. Use when asked to reflect on, review, or recap past work over a month or a configurable time range.
---

# Pulsar Reflect

Run `git log --since="<range>" --date=short --pretty='%ad %h %s'` with the user's range (default: 1 month). Include all branches with `--all` unless told otherwise. Read diffs only when a subject is unclear.

Output only this, newest day first, with no other text:

```
##### October 26

- `29a40fa` — Polished interfaces, catalog copy, and physics content.
- `cbfeda8` — Finished Calc III Exam 2 course distillation.
```

Use one `#####` header per day with commits, and exactly one bullet per commit: short hash, em dash, one past-tense sentence of at most about 12 words. List days with no commits only when asked.
