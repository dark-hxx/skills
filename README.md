# 🧠 skills

我的 **Hermes Agent** 技能合集，所有 AI Agent 通用。

## 技能列表

| 技能 | 说明 | 适用场景 |
|------|------|----------|
| [deals-hunter](deals-hunter/) | 薅羊毛 · 电商优惠券搜索 | 搜淘宝/京东红包口令、国补、优惠券 |

---

## 使用方法

### Hermes Agent 用户
将技能文件夹复制到 `~/.hermes/skills/` 即可：
```bash
cp -r deals-hunter ~/.hermes/skills/
```

### 其他 AI Agent 使用指南

每个技能目录下都提供两种文件：

| 文件 | 用途 |
|------|------|
| `SKILL.md` | Hermes 专用格式 |
| `deals-hunter-prompt.md` | **通用提示词**，任何 AI 都能用 |

#### Claude Code / Claude CLI
```bash
# 直接作为 prompt 传入
claude -p "$(cat deals-hunter/deals-hunter-prompt.md)"
# 或在对话中粘贴 deals-hunter-prompt.md 内容
```

#### OpenAI Codex CLI
```bash
# 将 prompt 内容作为系统提示词
codex --prompt "$(cat deals-hunter/deals-hunter-prompt.md)"
```

#### Cursor / Windsurf
- 将 `deals-hunter-prompt.md` 内容添加到项目的 `.cursorrules` 或 `Windsurf.md` 中
- 或在对话中直接粘贴

#### ChatGPT / Claude.ai / 其他聊天 AI
- 直接把 `deals-hunter-prompt.md` 的内容粘贴到对话中
- 告诉 AI："请按照这个提示词来帮我"

#### VS Code + Copilot / Continue.dev
- 在 `.github/copilot-instructions.md` 或 `.continuerc.json` 中引用 prompt 内容

---

## 协议
MIT