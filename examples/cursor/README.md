# Cursor Example

Cursor does not consume raw `SKILL.md` skills directly the same way Codex, Claude Code, and OpenClaw do. The closest native equivalent is a project rule in `.cursor/rules` or a root-level `AGENTS.md`.

Official docs:

- https://docs.cursor.com/en/context
- https://docs.cursor.com/en/cli/using

## Included Adaptations

- `first-love-persona.mdc`: Cursor project rule example
- `AGENTS.md`: Simpler root-level adaptation

## Install as a Project Rule

Copy:

```text
examples/cursor/first-love-persona.mdc
```

to:

```text
.cursor/rules/first-love-persona.mdc
```

Then apply it manually with `@first-love-persona`, or configure it according to your preferred Cursor rule mode.

## Install as AGENTS.md

Copy:

```text
examples/cursor/AGENTS.md
```

to your project root as:

```text
AGENTS.md
```

Use this path when you want a simpler, globally applied instruction file instead of MDC metadata.
