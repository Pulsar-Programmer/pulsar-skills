---
name: pulsar-create
description: Create or edit a concise skill in the pulsar-skills repository, install it for Codex and Claude Code, and commit and push after the user's OK.
---

# Pulsar Create

Create or edit `skills/<name>/SKILL.md` in the existing `pulsar-skills` repository, following its small-skill style: YAML name and description, then only essential instructions. Use the `pulsar-` prefix unless told otherwise. Validate the skill.

Install a copy in `~/.agents/skills/<name>` and symlink both `~/.codex/skills/<name>` and `~/.claude/skills/<name>` to it. Keep the installed copy identical to the repo version. Preserve unrelated existing files; stop on conflicting installs.

Show the final skill and installation paths. Honor any requested review before installing. Wait for the user's "OK" signal before committing and pushing; an OK approving the finished skill authorizes both. Commit only the skill's changes, then push the current branch to its remote and verify it is up to date. Mention any existing unpushed commits before approval, since the push will include them. Follow any explicit commit or push instructions already given without asking again.
