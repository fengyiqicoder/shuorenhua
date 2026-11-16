# 安装说明

## Claude Code

```bash
claude plugin marketplace add fengyiqicoder/shuorenhua
claude plugin install shuorenhua@shuorenhua
```

重启 Claude Code，输入 `/shuorenhua` 开启。

检查：`claude plugin list`
更新：`claude plugin marketplace update shuorenhua`，再重启
卸载：

```bash
claude plugin uninstall shuorenhua
claude plugin marketplace remove shuorenhua
```

## Codex

```bash
codex plugin marketplace add fengyiqicoder/shuorenhua --ref main
codex plugin add shuorenhua@shuorenhua
```

输入 `$shuorenhua` 开启。Codex 不会自动启用它。

检查：`codex plugin list`
卸载：

```bash
codex plugin remove shuorenhua
codex plugin marketplace remove shuorenhua
```

## Cursor、GitHub Copilot 和其他支持 Skill 的助手

```bash
npx skills add fengyiqicoder/shuorenhua          # 当前项目
npx skills add fengyiqicoder/shuorenhua -g       # 所有项目
npx skills add fengyiqicoder/shuorenhua -a cursor -y   # 只装给某一个助手
```

检查：`npx skills list`
卸载：`npx skills remove shuorenhua`

## Claude.ai / Claude 桌面版

1. 下载仓库里的 `skills/shuorenhua` 文件夹，压成 zip
2. 设置 → 功能 → Skills → 上传 Skill，选这个 zip
3. 对话里说"说人话模式"开启

## 手动安装

把 `skills/shuorenhua` 文件夹复制到助手的 skills 目录：

| 助手 | 目录 |
|---|---|
| Claude Code | `~/.claude/skills/` |
| Codex | `~/.codex/skills/` |
| 其他 | `~/.agents/skills/` |

## 一直开着（可选）

把下面这段粘进 `~/.claude/CLAUDE.md`（Claude Code）、`~/.codex/AGENTS.md`（Codex）或项目里的 `AGENTS.md`：

```markdown
## 输出风格

读者很忙，注意力有限。每条回复都要组织成拿到就能动手的样子：

1. 先给答案或下一步动作：命令、路径或代码放第一位。
2. 多步骤就编号，一步一个有边界的动作。
3. 结尾给一个两分钟内能做的下一步。
4. 先把当前问题做完，再提新问题。
5. 每轮重申进度（"第 3 步（共 5 步）完成"）。
6. 时间估计用具体单位，不说"一会儿"。
7. 改完之后，说出现在什么能用了。
8. 报错：写位置、原因和修法，不加情绪。
9. 列表最多 5 项。
10. 不铺垫，不总结，不客套收尾。

例外：被要求解释时完整解释。破坏性操作前先确认。连续三次修不好，停下来说出可能错了的假设。请求有歧义时，问一个简短的问题。
```
