---
name: pulsar-create
description: Create or edit a concise skill in the pulsar-skills repository; wait for the user's OK before installing it for Codex and Claude Code, committing, and pushing.
---

# Pulsar Create

Create or edit `skills/<name>/SKILL.md` in the existing `pulsar-skills` repository, following its small-skill style: YAML name and description, then only essential instructions. Use the `pulsar-` prefix unless told otherwise. Validate the skill.

Prepare and validate the repo changes first. Do not install, update installed copies, commit, or push until the user gives an explicit "OK" approving the finished skill. An OK approving the finished skill authorizes installation in all three locations, committing, and pushing. Follow explicit installation, commit, or push instructions already given without asking again.

Run `cat` on every created or edited `SKILL.md` and show its complete final contents in the reply, along with planned installation paths, every time before waiting for the user's "OK". Honor any requested review before installing. Mention any existing unpushed commits before approval, since the push will include them.

After approval, install a copy in `~/.agents/skills/<name>` and symlink both `~/.codex/skills/<name>` and `~/.claude/skills/<name>` to it. Keep the installed copy identical to the repo version. Preserve unrelated existing files; stop on conflicting installs. Commit only the approved skill changes, then push the current branch to its remote and verify it is up to date.
