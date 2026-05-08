# Schell Game Design / 谢尔游戏设计顾问

<p align="center">
  <img src="assets/schell-flow.svg" alt="Schell Game Design workflow" width="100%">
</p>

## 中文说明

这是一个用于游戏开发前期策划的 Agent Skill。它基于 Jesse Schell《游戏设计艺术》中的思考框架，帮助用户在开始写代码之前，先把游戏创意压实。

它不只适用于 Codex。任何能读取本地 `SKILL.md`、规则文件、自定义指令或项目级上下文的 coding agent，都可以使用它，例如 Codex、Claude Code、Cursor 以及其他类似工具。

它适合这些场景：

- 你有一个游戏点子，但还不确定它是否站得住。
- 你想在开发前检查玩法、故事、美术方向和技术限制是否互相支持。
- 你需要有人用直接、诚实的方式指出设计里的风险。
- 你希望把模糊的想法整理成可以原型验证的设计方向。

这个 Skill 会按阶段引导用户，而不是一次性给出一大堆建议：

1. **体验视角**：先确认玩家应该感受到什么。
2. **四要素审计**：检查机制、故事、美学和技术是否成立。
3. **核心回路压力测试**：确认最常重复的玩法本身是否有趣。
4. **玩家动机图**：区分玩家是因为乐趣回来，还是只被奖励牵着走。
5. **诚实评估**：指出有效部分、风险、缺失内容和下一步行动。

它不会替你直接写游戏代码。它的目标是在开发前帮助你少走弯路，先验证游戏设计是否值得继续投入。

## 安装方法

### Codex

安装到个人技能目录：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/threeaus/schell-game-design.git ~/.codex/skills/schell-game-design
```

使用时可以这样说：

```text
Use $schell-game-design to pressure-test my game idea before development.
```

### Claude Code

Claude Code 支持 `SKILL.md` 结构。可以安装为个人 Skill：

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/threeaus/schell-game-design.git ~/.claude/skills/schell-game-design
```

也可以安装到某个项目里，和团队共享：

```bash
mkdir -p .claude/skills
git clone https://github.com/threeaus/schell-game-design.git .claude/skills/schell-game-design
```

安装后重启 Claude Code，再让它列出可用 Skills，或直接让它帮你评估一个游戏创意。

### Cursor

Cursor 目前使用 Rules，而不是原生 `SKILL.md` 目录。推荐把这个 Skill 作为项目规则使用：

```bash
mkdir -p .cursor/rules
curl -L https://raw.githubusercontent.com/threeaus/schell-game-design/main/SKILL.md -o .cursor/rules/schell-game-design.mdc
```

如果你想长期在所有项目里使用，也可以打开 Cursor 的 User Rules，把 `SKILL.md` 里的主要内容复制进去。

### 其他 coding agent

如果你的工具支持本地技能、规则、记忆或自定义指令，可以用通用方式安装：

1. 下载或克隆这个仓库。
2. 找到 `SKILL.md`。
3. 把它放进该工具的 skills/rules/instructions 目录。
4. 如果工具不识别 `SKILL.md`，就把其中的正文复制到该工具的规则文件或自定义指令里。

只要 agent 能读取这份说明，它就可以按五个阶段辅助游戏开发前的策划。

## English

This is an Agent Skill for early-stage game planning. It uses Jesse Schell's *The Art of Game Design* lenses to help users pressure-test a game idea before development begins.

It is not limited to Codex. Any coding agent that can read local `SKILL.md` files, rule files, custom instructions, or project context can use it, including Codex, Claude Code, Cursor, and similar tools.

Use it when:

- You have a game idea but are not sure whether it is solid.
- You want to check whether mechanics, story, aesthetics, and technology support the same player experience.
- You need direct, honest design feedback before spending time building.
- You want to turn a vague concept into something that can be prototyped and tested.

The Skill guides the user step by step instead of overwhelming them with a full design lecture:

1. **Experience Lens**: define what the player should feel.
2. **Four Elements Audit**: evaluate mechanics, story, aesthetics, and technology.
3. **Core Loop Stress Test**: check whether the repeated play action is satisfying on its own.
4. **Player Motivation Map**: separate intrinsic motivation from external rewards.
5. **Honest Assessment**: identify strengths, risks, missing pieces, and next steps.

This Skill does not build the game or write production code. Its purpose is to help you validate the design direction before development starts.

## Installation

### Codex

Install as a personal skill:

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/threeaus/schell-game-design.git ~/.codex/skills/schell-game-design
```

Example prompt:

```text
Use $schell-game-design to pressure-test my game idea before development.
```

### Claude Code

Claude Code supports the `SKILL.md` structure. Install it as a personal Skill:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/threeaus/schell-game-design.git ~/.claude/skills/schell-game-design
```

Or install it inside a project so it can be shared with a team:

```bash
mkdir -p .claude/skills
git clone https://github.com/threeaus/schell-game-design.git .claude/skills/schell-game-design
```

Restart Claude Code after installation, then ask it to list available Skills or use the Skill with a game idea.

### Cursor

Cursor uses Rules rather than native `SKILL.md` folders. The recommended approach is to install this Skill as a project rule:

```bash
mkdir -p .cursor/rules
curl -L https://raw.githubusercontent.com/threeaus/schell-game-design/main/SKILL.md -o .cursor/rules/schell-game-design.mdc
```

For global use, open Cursor User Rules and paste the main contents of `SKILL.md` there.

### Other coding agents

For any agent that supports local skills, rules, memories, or custom instructions:

1. Download or clone this repository.
2. Locate `SKILL.md`.
3. Place it in the tool's skills/rules/instructions directory.
4. If the tool does not recognize `SKILL.md`, copy the body into that tool's rule file or custom instruction area.

If the agent can read the instructions, it can use the five-stage workflow to support pre-development game planning.

## Files

- `SKILL.md`: the Skill instructions.
- `agents/openai.yaml`: interface metadata for Codex.
- `assets/schell-flow.svg`: a hand-authored workflow diagram used by this README.

## References

- Claude Code Agent Skills: https://docs.claude.com/en/docs/claude-code/skills
- Cursor Rules: https://docs.cursor.com/context/rules

## Repository

GitHub: https://github.com/threeaus/schell-game-design
