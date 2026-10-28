# Pulsar Skills

Personal agent skills by [Pulsar-Programmer](https://github.com/Pulsar-Programmer), kept together under the `pulsar-` prefix.

## Install

Use the [skills CLI](https://skills.sh/docs) with Node.js and npm:

```sh
npx skills add Pulsar-Programmer/pulsar-skills
```

Install just the feature audit:

```sh
npx skills add Pulsar-Programmer/pulsar-skills --skill pulsar-feature-audit
```

The CLI lets you choose your agent and installs into the current project by default. For a global Codex install:

```sh
npx skills add Pulsar-Programmer/pulsar-skills --skill pulsar-feature-audit --agent codex --global
```

Preview available skills without installing:

```sh
npx skills add Pulsar-Programmer/pulsar-skills --list
```

This repository uses the standard Agent Skills layout, `skills/<skill-name>/SKILL.md`. No custom installer or npm package is required.

## pulsar-feature-audit

A read-only audit of a commit and the visuals it introduces. The agent identifies the commit, runs the app, exercises each visible change, and presents sharp screenshots with findings and coverage gaps. It never implements fixes.

After installing, ask your agent:

```text
/pulsar-feature-audit <commit-sha>
```

In Codex, invoke it with:

```text
$pulsar-feature-audit Audit commit <commit-sha> and show every visible change in action.
```

Invocation syntax and skill discovery depend on the host. The skill needs a coding agent with repository, local server, browser, and screenshot access; this is not a ChatGPT GPT Store app.

## pulsar-ux-reuse

Reuse existing UI components across the codebase. Do not create your own. Frontend changes move, wire, or reuse existing UI.

Install for Claude Code and Codex at user scope:

```sh
npx skills add Pulsar-Programmer/pulsar-skills --skill pulsar-ux-reuse --agent claude-code codex --global
```

Invoke with `/pulsar-ux-reuse` in Claude Code or `$pulsar-ux-reuse` in Codex.

## Add another skill

Create `skills/pulsar-<name>/SKILL.md` with YAML `name` and `description` fields followed by the instructions. Keep the folder and skill name identical. Optional `agents/openai.yaml` metadata can provide a friendly name and starter prompt for compatible hosts.

## License

MIT
