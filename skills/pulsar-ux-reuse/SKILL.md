---
name: pulsar-ux-reuse
description: Reuse existing UI components across the codebase. Do not create your own. Use for frontend work that moves, wires, or composes existing UI without inventing components, layouts, or styles.
---

# Pulsar UX Reuse

Reuse existing UI components across the codebase. Do not create your own. Treat frontend work as moving, reusing, and wiring what already exists.

## Find the existing UI first

- Inspect the target screen, nearby screens, shared components, and their call sites before editing.
- Search the whole codebase for the requested control, section, layout, and interaction. Include existing packages, examples, and component stories when present.
- Follow the existing implementation and its public props, variants, slots, and composition patterns. Use existing styling, tokens, icons, assets, and responsive behavior.

## Reuse only

- Import and render existing components. Move existing UI to the requested location or compose it using established layout components and patterns.
- Add only the minimal imports, props, data bindings, event handlers, and placement changes needed for the requested behavior.
- If suitable UI is embedded in another screen, extract that exact implementation into a shared component and update its original caller. Preserve its appearance and behavior; do not redesign it during extraction.
- Do not write fresh UI markup, components, layouts, CSS, utility-class recipes, animations, icons, or visual variants. Do not recreate an existing component inline or wrap it to introduce custom styling.
- Do not install a UI library, copy components from outside the codebase, or generate a new frontend to fill a gap.
- Reuse existing primitives only through combinations already established in the codebase. Having buttons and cards available does not authorize designing a new screen from them.

## When reuse cannot satisfy the request

Complete any independent reuse work, then identify the missing component or unsupported capability and cite the closest existing implementation. Ask for explicit permission before creating new UI. Do not silently fall back to building it yourself.

An ordinary request to add a feature or make something look better does not waive this constraint. If the user explicitly authorizes new UI, keep that exception limited to what they authorized.

## Verify and report

Use the project's relevant checks to verify imports, callers, and behavior. When moving or extracting UI, verify the original usage still works where it should remain.

Report which existing components were reused or moved, where they came from, and any remaining gap. Keep the change limited to the requested reuse.
