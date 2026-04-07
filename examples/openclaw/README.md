# OpenClaw Example

OpenClaw supports AgentSkills-compatible folders and can load `SKILL.md` skills from multiple locations.

Official docs:

- https://docs.openclaw.ai/tools/skills

## Common Install Locations

- Workspace skills: `./skills/first-love-persona`
- Project agent skills: `./.agents/skills/first-love-persona`
- Personal agent skills: `~/.agents/skills/first-love-persona`
- Shared managed skills: `~/.openclaw/skills/first-love-persona`

## Install

Copy the portable skill folder:

```text
../../plugins/first-love-persona/skills/first-love-persona
```

into any of the locations above.

## Invocation

OpenClaw can expose installed skills to the agent automatically. Depending on your setup, you can invoke the skill by naming it in the prompt or by using the runtime's skill command surface if enabled.
