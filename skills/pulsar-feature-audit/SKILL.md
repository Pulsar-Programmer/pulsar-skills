---
name: pulsar-feature-audit
description: Audit a given commit and its visible changes by running the app, exercising changed features, and presenting sharp screenshots with findings. Use for commit audits and visual feature walkthroughs. Read-only; never implement fixes.
---

# Pulsar Feature Audit

Audit the given commit and show every user-visible change in action. Identify the commit by its hash and subject, show what the features look like, and report defects with evidence. This is a read-only audit.

## Boundaries

- Do not edit source, configuration, dependencies, lockfiles, or tracked files; do not commit, push, deploy, or implement fixes.
- Running the local server and writing screenshots, logs, or build caches is allowed. Store audit artifacts outside the source tree when possible.
- Use disposable local data for interactions that change application state. Do not send messages, purchase, delete real data, or mutate shared/production services.
- Preserve the user's checkout and uncommitted work. If the requested commit is not checked out, use a temporary detached worktree or equivalent isolated snapshot; never reset or switch their working checkout.
- If setup requires source changes, missing credentials, or unavailable infrastructure, report the blocker and continue any independent checks. Do not silently modify the project to make the audit pass.

## Identify what changed

1. Resolve the supplied commit to its full SHA and read its subject, diff, and relevant surrounding code. If no commit was supplied or the ref is ambiguous, ask which commit to audit.
2. Compare with its parent by default. For merge commits, state which parent is used; ask if the intended comparison is unclear.
3. Map every user-visible change to its route or screen, trigger, expected result, and relevant states. Group files belonging to the same feature. Mark internal-only changes separately rather than inventing visual evidence.
4. Verify the server will actually run the audited revision. Record the running SHA and disclose any uncommitted changes or environment differences that could affect the result. Do not present screenshots from another revision as evidence.

## Run and exercise the app

- Read the project's run instructions and scripts, then start the documented local server or reuse a verified server for the target revision. Use the project's existing setup and lockfile. Keep the server local; if dependencies are missing, install only in the disposable audit workspace without changing the lockfile.
- Use the environment's preferred browser tools. In T3 Code, check `preview_status`, open a preview if necessary, and inspect pages with `preview_snapshot`; follow browser ownership rules. Elsewhere, use the available browser automation.
- Open the affected routes and perform the real interactions. A landing-page screenshot alone does not verify an interactive feature. Capture meaningful states such as before/after an interaction, open menus or dialogs, validation, and loading/empty/error/success states when the commit affects them and they are reproducible.
- Check appropriate desktop and mobile widths for changed responsive layouts. Inspect relevant console or network failures and connect them to observed behavior.
- Compare with the parent revision when needed to establish whether behavior is a regression. Label before/after screenshots by revision and use matching viewport, data, and interaction state.

## Capture clear visual evidence

- Capture actual browser screenshots; never generate or recreate the UI as a substitute for evidence.
- Wait for the relevant content, fonts, and images to load and for transitions to settle. For motion changes, capture several meaningful stages or add a short recording alongside the screenshots.
- Capture at native resolution with readable text. Do not upscale, stretch, or apply blur. Use focused viewport captures or crops when a full-page image would become unreadable in the response.
- Open and inspect every screenshot before presenting it. Retake blurry, clipped, blank, obscured, or premature captures. If the app itself renders blurry content, report that defect instead of disguising it.
- Give screenshots descriptive filenames, such as `<short-sha>-settings-dialog-open-desktop.png`. Avoid exposing credentials or personal data; prefer test data and frame captures accordingly.
- Cover every distinct visible change with enough screenshots to demonstrate the relevant behavior. Explicitly list any missing coverage and its reason.

## Present the audit

Start with **Pulsar Feature Audit — `<short SHA>`: `<commit subject>`**, followed by the verdict and the revision, comparison base, URL, and viewports actually inspected.

Show the screenshots inline using the host's supported image syntax, with a short caption identifying the feature, action, and observed result. Include real image attachments or accessible image links; a list of filenames alone is not a visual walkthrough. Group the evidence by feature and include a compact coverage list so every visible change can be accounted for.

Report actionable findings in severity order. For each, include the symptom, reproduction steps, expected versus observed result, screenshot evidence when relevant, and a precise code location where supported. Distinguish observed defects from code-only concerns. Do not claim a successful check for a blocked or untested state.

Finish with limitations and unverified changes. If no defects were found, say so while keeping the evidence and coverage. Stop after the audit; do not fix anything.
