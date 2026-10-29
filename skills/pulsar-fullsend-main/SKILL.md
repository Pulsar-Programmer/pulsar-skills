---
name: pulsar-fullsend-main
description: Commit the current work, merge it into local main, then delete the current worktree and branch. Use when asked to fullsend or commit, merge to main, and clean up.
---

# Pulsar Fullsend Main

Invocation authorizes the commit, local merge, and cleanup without another confirmation.

1. Identify the current branch, worktree, and main checkout. Preserve unrelated changes; stop if the intended changes are ambiguous.
2. Run relevant project checks and commit the intended changes. Stop on failures.
3. Merge the branch into local `main` when the changes are compatible; the main checkout does not need to be clean. Preserve existing uncommitted changes. Reconcile overlapping changes or merge conflicts only after confirming that no other agent is editing the affected files while you do so. Stop if that cannot be confirmed or the changes cannot be reconciled safely. Never force or discard work.
4. Verify main contains the commit. From a surviving checkout, remove the clean task worktree if it is a linked worktree, then delete the merged branch with `git branch -d`. Never delete the primary checkout or `main`.
5. Report the commit and cleanup. Push or delete remote branches only when requested.
