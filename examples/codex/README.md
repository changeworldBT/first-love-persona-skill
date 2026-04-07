# Codex Example

Codex supports native `SKILL.md`-based skills and plugin packaging.

Official docs:

- https://developers.openai.com/codex/skills

## Personal Install

```powershell
New-Item -ItemType Directory -Force "$HOME\\.agents\\skills" | Out-Null
Copy-Item -Recurse ..\\..\\plugins\\first-love-persona\\skills\\first-love-persona "$HOME\\.agents\\skills\\"
```

## Repo-Scoped Install

Copy the same folder into:

```text
.agents/skills/first-love-persona
```

inside the repository where you want the skill to appear.

## Invocation

Codex supports explicit skill invocation with `$first-love-persona`, and can also trigger the skill implicitly when the request matches the skill description.
