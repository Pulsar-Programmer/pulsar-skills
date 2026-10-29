---
name: pulsar-fullsend-main
description: Commit the current work, merge it into local main, then delete the current worktree and branch. Use when asked to fullsend or commit, merge to main, and clean up.
---

# Pulsar Fullsend Main

Invocation authorizes the commit, local merge, and cleanup without another confirmation.

1. Identify the current branch, worktree, and main checkout. Preserve unrelated changes; stop if the intended changes are ambiguous.
2. Run relevant project checks and commit the intended changes. Stop on failures.
3. Merge the branch into local `main` from a clean checkout. Stop on conflicts; never force or discard work.
4. Verify main contains the commit. From a surviving checkout, remove the clean task worktree if it is a linked worktree, then delete the merged branch with `git branch -d`. Never delete the primary checkout or `main`.
5. Report the commit and cleanup. Push or delete remote branches only when requested.
