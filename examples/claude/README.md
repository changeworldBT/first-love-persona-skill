# Claude Code Example

Claude Code supports native skill folders with `SKILL.md` entrypoints.

Official docs:

- https://code.claude.com/docs/en/skills

## Personal Install

```bash
mkdir -p ~/.claude/skills
cp -R ../../plugins/first-love-persona/skills/first-love-persona ~/.claude/skills/
```

## Project Install

Copy the skill into:

```text
.claude/skills/first-love-persona
```

inside the project where you want Claude Code to load it.

## Invocation

Claude can load the skill automatically when the description matches, or invoke it directly as:

```text
/first-love-persona
```
