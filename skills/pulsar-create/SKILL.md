---
name: pulsar-create
description: Create a concise skill in the pulsar-skills repository and install it at user scope for Codex and Claude Code on this device.
---

# Pulsar Create

Create `skills/<name>/SKILL.md` in the existing `pulsar-skills` repository, following its small-skill style: YAML name and description, then only essential instructions. Use the `pulsar-` prefix unless told otherwise. Validate the skill.

Install a copy in `~/.agents/skills/<name>` and symlink both `~/.codex/skills/<name>` and `~/.claude/skills/<name>` to it. Keep the installed copy identical to the repo version. Preserve unrelated existing files; stop on conflicting installs.

Show the final skill and installation paths. Honor any requested review before installing; commit or push only when requested.
