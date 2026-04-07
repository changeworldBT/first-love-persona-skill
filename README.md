# First Love Persona Skill

Configurable fictional "first love" persona skill for warm conversation and competent task execution.

This repository packages the skill in a plugin marketplace-friendly layout, so it can be shared through GitHub or copied directly into a supported agent's skill directory.

## What It Does

- Speaks in a gentle, intimate, believable tone instead of sounding like a template
- Keeps practical capability intact for chat, writing, planning, coding, and tool use
- Lets each user override name, gender, age, personality, hobbies, memory background, and speaking style
- Treats the default profile as a fallback, not a hard lock

## Repository Structure

- `.agents/plugins/marketplace.json`: Marketplace manifest for GitHub-backed plugin discovery
- `plugins/first-love-persona/.codex-plugin/plugin.json`: Plugin manifest
- `plugins/first-love-persona/skills/first-love-persona/`: The reusable skill payload

## Install

### Plugin Marketplace

After publishing this repository to GitHub, install it from a marketplace-capable client with the repository path:

```text
/plugin marketplace add changeworldBT/first-love-persona-skill
/plugin install first-love-persona@first-love-persona
```

### OpenAI Codex

Copy the skill folder into your Codex skills directory:

```powershell
Copy-Item -Recurse .\plugins\first-love-persona\skills\first-love-persona "$HOME\.codex\skills\"
```

### Clone / Copy

Any agent that supports the Agent Skills pattern can use the skill by copying:

```text
plugins/first-love-persona/skills/first-love-persona
```

into its local skills directory.

## Usage

### Basic

```text
Use $first-love-persona 和我说话，并帮我安排今天的事情。
```

### Configure Persona

```text
Use $first-love-persona。名字叫晚晚，22 岁，性格温柔但会轻一点逗我，喜欢夜雨和咖啡，说话自然一点。
```

### Practical Task

```text
Use $first-love-persona，保持这个人设，但帮我把这段文案改得更克制一点。
```

### Technical Task

```text
Use $first-love-persona，在不降低准确性的前提下，帮我 review 这个 Python 脚本。
```

## Behavior Model

The skill resolves persona settings in this order:

1. Explicit settings in the current request
2. Persona settings already established in the current thread
3. Default values from `references/profile.md`

It only treats the current thread as session memory. It does not claim cross-session persistent memory unless the user is clearly asking for fiction.

## Publish Status

This repository is prepared for publication at:

```text
https://github.com/changeworldBT/first-love-persona-skill
```
