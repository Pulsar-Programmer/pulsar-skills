---
name: pulsar-select-image
description: Start a local server, provide direct links, and capture screenshots of every selected UI change or feature.
---

# Pulsar Select Image

Use the selected changes or features from the conversation; ask only if unclear. Start the app's local server, or reuse a running one, and leave it running for review.

Verify and provide a clickable localhost URL directly to each selected change, including any route, query, or anchor needed. Briefly label each link. If a state cannot be linked directly, give the nearest URL and exact steps to reach it. Report blockers; do not invent working links.

Capture a screenshot of each selected UI change or feature in its relevant visible state. Add a clearly visible red outline circle around the area the user should look at, without obscuring the change. Inspect each annotated image to ensure the circle highlights the correct area and the change is clearly shown, save it as a PNG, and include its labeled image and file link alongside the corresponding localhost URL. Skip screenshots for non-UI changes and report any UI states that could not be captured.

Save screenshots outside the repository; do not stage, commit, or push generated images.

Preserve source and uncommitted work. Do not implement fixes.
