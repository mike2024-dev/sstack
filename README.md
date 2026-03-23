# sstack

A cognitive framework for building polished marketing pages with AI coding tools. Like [gstack](https://github.com/nichochar/gstack) for UI design.

用于 AI 编程工具的 UI 设计认知框架。把 AI 生成的"模板感"页面变成专业设计。

**sstack** encodes the design instincts of [Steve Schoger](https://x.com/steveschoger) into a structured decision system that any coding agent can follow — turning generic AI output into intentional, polished work.

**sstack** 将 [Steve Schoger](https://x.com/steveschoger) 的设计直觉编码成结构化决策系统，让任何编程 Agent 都能按框架产出专业级 UI。

---

[English](#what-it-does) | [中文](#它做什么)

---

## What It Does

4 cognitive gears, run in order:

| Gear | Name | What It Does |
|------|------|-------------|
| 1 | **Foundation** | Fix layout, kill centering, set up grid structure |
| 2 | **Typography + Color** | Lock the font system, fix tracking, set neutral palette |
| 3 | **Components + Details** | Pixel-perfect buttons, screenshot wells, testimonial redesign |
| 4 | **Polish + Validation** | Global patterns, orphan prevention, final audit |

Each gear includes:
- **Decision trees** — IF/THEN logic, not vague guidelines
- **Anti-pattern triggers** — 🚨 signs something is wrong
- **Specific Tailwind values** — exact classes, not "make it look better"
- **Copy-pasteable AI prompts** — ready to drop into Claude Code, Cursor, etc.

## 它做什么

4 个认知档位，按顺序执行：

| 档位 | 名称 | 做什么 |
|------|------|--------|
| 1 | **基础** | 修复布局、消灭居中、建立网格结构 |
| 2 | **字体 + 配色** | 锁定字体系统、修正字距、设置中性色板 |
| 3 | **组件 + 细节** | 像素级按钮、截图容器、推荐语重设计 |
| 4 | **抛光 + 验证** | 全局模式应用、孤字防治、最终审计 |

每个档位包含：
- **决策树** — IF/THEN 逻辑，不是模糊指南
- **反模式触发器** — 🚨 出了问题的信号
- **具体 Tailwind 值** — 确切的 class，不是"让它更好看"
- **可直接复制的 AI Prompt** — 直接粘贴到 Claude Code、Cursor 等工具

---

## Quick Example / 快速示例

**Before** (typical AI output / 典型 AI 输出):
```html
<button class="bg-indigo-600 text-white px-4 h-10 rounded-md shadow-lg border border-indigo-700">
```

**After** (sstack-guided / sstack 指导后):
```html
<button class="bg-gray-950 text-white text-sm py-2.5 px-5 rounded-full shadow ring-1 ring-gray-950/10">
```

The 4 changes that eliminate 80% of "template-y" perception:

消除 80% "AI 模板感"的 4 个关键改动：

| # | AI Default / AI 默认 | sstack Fix / sstack 修复 |
|---|-----------|-----------|
| 1 | Inter from Google Fonts | Variable Inter from [rsms.me/inter](https://rsms.me/inter/) |
| 2 | Indigo accent color / 靛蓝强调色 | `gray-950` or deliberate brand color / 或品牌色 |
| 3 | Solid border + shadow / 实色边框+阴影 | `ring-1 ring-gray-950/10` |
| 4 | Off-white section backgrounds / 灰白交替背景 | White only, canvas grid / 纯白+画布网格 |

---

## Installation / 安装

### Claude Code / Codex Skills

```bash
# Copy the skill to your skills directory
# 复制 skill 到你的 skills 目录
git clone https://github.com/mike2024-dev/gstack.git ~/.claude/skills/sstack

# Or just download SKILL.md / 或只下载 SKILL.md
curl -o ~/.claude/skills/sstack/SKILL.md https://raw.githubusercontent.com/mike2024-dev/gstack/main/SKILL.md
```

### OpenClaw

```bash
cp -r sstack/ ~/.openclaw/workspace/skills/sstack/
```

### Manual / 手动使用

Just read `SKILL.md` and the `references/` folder. The framework works whether you use it with an AI agent or apply it manually.

直接阅读 `SKILL.md` 和 `references/` 目录。无论是用 AI agent 还是手动应用都有效。

---

## File Structure / 文件结构

```
sstack/
├── SKILL.md                              # Entry point / 入口 (204 lines)
│   ├── 4-gear overview + gates           # 4 档位概览 + 门控条件
│   ├── 9-step end-to-end workflow        # 9 步端到端工作流
│   ├── Anti-pattern quick scan           # 反模式快速扫描
│   └── Navigation to reference files     # 参考文件导航
└── references/
    ├── gear-1-foundation.md              # Layout, structure, canvas grid / 布局、结构、画布网格
    ├── gear-2-typography-color.md        # Font system, tracking, palette / 字体系统、字距、色板
    ├── gear-3-components.md              # Buttons, screenshots, testimonials / 按钮、截图、推荐语
    ├── gear-4-polish.md                  # Global patterns, final audit / 全局模式、最终审计
    ├── cheat-sheets.md                   # Quick reference tables / 速查表 (Tailwind values)
    └── ai-collaboration.md              # Prompt templates, iteration strategy / Prompt 模板、迭代策略
```

---

## Origin / 来源

This framework is distilled from [Steve Schoger's](https://x.com/steveschoger) video **"Designing with Claude Code"**, where he live-designs a complete marketing page from scratch in ~60 minutes, demonstrating the exact design instincts that separate professional work from AI-generated templates.

本框架提炼自 [Steve Schoger](https://x.com/steveschoger) 的视频 **"Designing with Claude Code"**，他在约 60 分钟内从零开始现场设计了一个完整的营销页面，展示了区分专业设计与 AI 模板的精准设计直觉。

We extracted every principle, technique, and anti-pattern from the full transcript (1180 entries), classified each as "universal design principle" vs "personal preference," and organized them into a cognitive framework.

我们从完整字幕（1180 条）中提取了每一个原则、技巧和反模式，将每条分类为"通用设计原则"或"个人偏好"，并组织成认知框架。

---

## Credits & Acknowledgments / 致谢

### Steve Schoger

The design methodology in sstack is based entirely on Steve Schoger's work and teachings. Steve is the designer behind [Tailwind UI](https://tailwindui.com/) and co-author of [Refactoring UI](https://www.refactoringui.com/).

sstack 中的设计方法论完全基于 Steve Schoger 的作品和教学。Steve 是 [Tailwind UI](https://tailwindui.com/) 的设计师，也是 [Refactoring UI](https://www.refactoringui.com/) 的合著者。

- 🎥 **Source video / 源视频**: [Designing with Claude Code](https://www.youtube.com/watch?v=lkKGQVHrXzE)
- 🛠️ **UI.sh**: [ui.sh](https://ui.sh) — Steve's upcoming skills toolkit for coding agents (with Adam Wathan & the Tailwind team) / Steve 即将推出的编程 Agent 设计技能工具包
- 🐦 **Twitter/X**: [@steveschoger](https://x.com/steveschoger)
- 🎨 **Heroicons**: [heroicons.com](https://heroicons.com/)
- 📘 **Refactoring UI**: [refactoringui.com](https://www.refactoringui.com/)

### Inspiration / 灵感来源

- [gstack](https://github.com/nichochar/gstack) by Garry Tan — the cognitive gear framework that inspired sstack's structure / 启发了 sstack 认知档位结构的框架
- [autoresearch](https://github.com/karpathy/autoresearch) by Andrej Karpathy — autonomy principles behind the build process / 构建过程中的自主性原则
- [OpenClaw](https://github.com/openclaw/openclaw) — the multi-agent platform used to orchestrate the build / 用于编排构建的多 Agent 平台

---

## How It Was Built / 构建过程

sstack was built by a team of AI agents orchestrated by [OpenClaw](https://github.com/openclaw/openclaw):

sstack 由 [OpenClaw](https://github.com/openclaw/openclaw) 编排的 AI Agent 团队构建：

1. **Researcher** (Sonnet) — extracted 17 universal principles + 8 preferences + 12 anti-patterns from 1180 transcript entries / 从 1180 条字幕中提取 17 个通用原则 + 8 个偏好 + 12 个反模式
2. **Plan Reviewers** (Gemini Pro + Sonnet) — stress-tested the plan before execution / 在执行前对方案进行压力测试
3. **Architect** (Sonnet) — designed the 4-gear cognitive framework / 设计 4 档位认知框架
4. **Skill Author** (Sonnet) — packaged into AgentSkill format / 打包为 AgentSkill 格式
5. **Tester** (Sonnet) — validated against a sample page (24/24 issues caught) / 用示例页面验证（24/24 问题全部捕获）
6. **Codex** (GPT) — built a complete landing page following the skill to verify production quality / 按 skill 构建完整 landing page 验证生产质量

Total time: ~45 minutes. Zero human code written.

总耗时：约 45 分钟。零人工代码。

---

## License

MIT

---

## Contributing / 贡献

PRs welcome. Especially / 欢迎 PR，特别是：

- Additional techniques from other Schoger videos or Refactoring UI / 来自 Schoger 其他视频或 Refactoring UI 的技巧
- Techniques from other designers (as separate gear extensions) / 其他设计师的技巧（作为独立档位扩展）
- Improvements to decision trees based on real-world usage / 基于实际使用改进决策树
- Dark mode / responsive / accessibility gear extensions / 暗黑模式 / 响应式 / 无障碍档位扩展
