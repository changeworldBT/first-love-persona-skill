# 初恋-Skill

[English](./README.md)

这是一个可配置的“初恋”虚构人设 skill，用于温柔自然的对话，同时保留正常完成任务的能力。

这个仓库首先按通用 Agent Skills 结构组织，同时附带 Codex/OpenAI 可识别的插件和 marketplace 元数据。因此更准确地说，它是“核心 skill 通用，平台包装可选”。

![First Love Persona 封面](./assets/cover.png)

## 哪些部分是通用的

- `plugins/first-love-persona/skills/first-love-persona/` 是真正可复用的 skill 本体
- `SKILL.md` 和 `references/profile.md` 是跨 agent 的核心文件
- `.codex-plugin/plugin.json`、`.agents/plugins/marketplace.json`、`agents/openai.yaml` 属于特定生态的集成元数据

## 兼容性说明

这个仓库可以分成两层理解：

- 核心 skill：对于支持 `SKILL.md` 风格技能的 agent，通常可以复用
- 平台包装：只对理解 Codex/OpenAI 插件或 marketplace 元数据的运行时生效

所以结论是：

- OpenAI Codex 可以同时使用 skill 本体和仓库里的插件包装
- 其他兼容 skill 的 agent 通常可以通过手动复制 skill 文件夹来使用
- 即使 skill 内容可复用，不同客户端的触发语法也可能不同
- marketplace 安装方式并不是所有 agent 都支持

## 预览图

![跨平台截图](./assets/screenshot-platforms.png)

## 功能特性

- 用温柔、亲近、不过分模板化的语气交流
- 不牺牲正常能力，仍可处理聊天、写作、规划、编码和工具调用
- 允许用户覆盖名字、性别、年龄、性格、爱好、记忆背景和说话方式
- 默认档案只是兜底，不是硬编码身份
- 只把当前线程当作会话记忆，不伪造跨会话持久记忆

## 仓库结构

- `assets/`：GitHub 和 marketplace 展示用的封面图、截图资源
- `.agents/plugins/marketplace.json`：适用于支持插件市场的运行时
- `plugins/first-love-persona/.codex-plugin/plugin.json`：Codex/OpenAI 插件元数据
- `plugins/first-love-persona/skills/first-love-persona/`：真正可复用的 skill
- `examples/`：分平台安装说明和适配示例

## 安装方式

### Plugin Marketplace

如果你的客户端支持从 GitHub 安装 plugin marketplace：

```text
/plugin marketplace add changeworldBT/first-love-persona-skill
/plugin install first-love-persona@first-love-persona
```

### OpenAI Codex

根据 Codex 官方 skills 文档，个人安装和仓库安装都使用 `.agents/skills` 目录。个人安装可以这样做：

```powershell
Copy-Item -Recurse .\plugins\first-love-persona\skills\first-love-persona "$HOME\.agents\skills\"
```

### 通用手动复制

对于支持 skills 的其他 agent，复制下面这个目录即可：

```text
plugins/first-love-persona/skills/first-love-persona
```

复制到对应 agent 的本地 skills 目录中。

## 平台说明

- Codex: [examples/codex/README.md](./examples/codex/README.md)
- Claude Code: [examples/claude/README.md](./examples/claude/README.md)
- Cursor: [examples/cursor/README.md](./examples/cursor/README.md)
- OpenClaw: [examples/openclaw/README.md](./examples/openclaw/README.md)

## 使用方式

### 通用调用

具体触发语法取决于客户端。如果客户端支持显式 skill 名称，可以这样写：

```text
Use $first-love-persona 和我说话，并帮我安排今天的事情。
```

### 配置人设

```text
Use $first-love-persona。名字叫晚晚，22 岁，性格温柔但会轻一点逗我，喜欢夜雨和咖啡，说话自然一点。
```

### 写作或改写任务

```text
Use $first-love-persona，保持这个人设，但帮我把这段文案改得更克制一点。
```

### 技术任务

```text
Use $first-love-persona，在不降低准确性的前提下，帮我 review 这个 Python 脚本。
```

## 行为模型

skill 会按这个优先级确定当前人设：

1. 当前请求里明确指定的设定
2. 当前线程中已经建立的人设设定
3. `references/profile.md` 中的默认值

这个 skill 只把当前线程当作会话记忆。除非用户明确要求进入虚构叙事，否则不应声称自己拥有跨会话持久记忆。

## 包含的文件

- `SKILL.md`：触发描述和运行规则
- `references/profile.md`：默认人设模板和可配置字段
- `agents/openai.yaml`：OpenAI 兼容界面的可选 UI 元数据

## 官方文档

- OpenAI Codex skills: https://developers.openai.com/codex/skills
- Claude Code skills: https://code.claude.com/docs/en/skills
- Cursor rules: https://docs.cursor.com/en/context
- OpenClaw skills: https://docs.openclaw.ai/tools/skills

## GitHub

仓库地址：

```text
https://github.com/changeworldBT/first-love-persona-skill
```
