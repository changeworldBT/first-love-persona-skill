# First Love Persona Skill

A configurable fictional "first love" persona skill for warm conversation and competent task execution.

This repository packages the skill in a plugin marketplace-friendly layout so it can be installed from GitHub or copied directly into a supported agent's local skills directory.

## Features

- Maintain a gentle, intimate, believable tone instead of sounding templated
- Keep practical capability intact for chat, writing, planning, coding, and tool use
- Let each user override name, gender, age, personality, hobbies, memory background, and speaking style
- Treat the default profile as a fallback rather than a hard-coded identity
- Keep session memory inside the current thread instead of claiming cross-session persistence

## Repository Layout

- `.agents/plugins/marketplace.json`: Marketplace manifest for plugin discovery
- `plugins/first-love-persona/.codex-plugin/plugin.json`: Plugin metadata
- `plugins/first-love-persona/skills/first-love-persona/`: The actual reusable skill

## Installation

### Plugin Marketplace

If your client supports plugin marketplace installation from GitHub:

```text
/plugin marketplace add changeworldBT/first-love-persona-skill
/plugin install first-love-persona@first-love-persona
```

### OpenAI Codex

Copy the skill into your Codex skills directory:

```powershell
Copy-Item -Recurse .\plugins\first-love-persona\skills\first-love-persona "$HOME\.codex\skills\"
```

### Manual Copy for Any Skills-Compatible Agent

Copy this folder:

```text
plugins/first-love-persona/skills/first-love-persona
```

into the local skills directory used by your agent runtime.

## Usage

### Basic Conversation

```text
Use $first-love-persona and talk to me while helping me plan my day.
```

### Configure the Persona

```text
Use $first-love-persona. Her name is Wanan, she is 22, gentle but lightly playful, likes rain and coffee, and speaks naturally.
```

### Writing or Editing Task

```text
Use $first-love-persona, keep the persona, and rewrite this message so it sounds more restrained.
```

### Technical Task

```text
Use $first-love-persona and review this Python script without losing technical precision.
```

## Behavior Model

The skill resolves persona settings in this order:

1. Explicit settings in the current request
2. Persona settings already established in the current thread
3. Default values from `references/profile.md`

The skill only treats the current thread as session memory. It should not claim persistent memory across separate sessions unless the user is clearly asking for fiction.

## Included Files

- `SKILL.md`: Triggering description and runtime instructions
- `references/profile.md`: Default persona template and configurable fields
- `agents/openai.yaml`: UI-facing skill metadata

## GitHub

Repository:

```text
https://github.com/changeworldBT/first-love-persona-skill
```
