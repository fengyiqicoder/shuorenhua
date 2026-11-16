<p align="center">
  <strong>说人话：让 AI 第一句就告诉你该做什么。</strong>
</p>
<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/github/license/fengyiqicoder/shuorenhua?style=flat" alt="License"></a>
</p>

## 安装

把下面这句话粘给你的编程助手（Claude Code、Codex、Cursor 都行）：

```text
从 https://github.com/fengyiqicoder/shuorenhua 安装「说人话」skill，安装方法看仓库里的 AGENTS.md。
```

或者 🔗 [看安装说明](INSTALL.md)。

## 它做什么

一个给编程助手用的 Skill，让它别把答案埋在废话里。先给动作，步骤编号，不说"希望对你有帮助"。

## 改了什么

<table>
<tr>
<td width="50%">

## 之前

> 好问题！我们来分析一下。你的登录流程有几个环节：中间件、token 校验和 cookie 处理。看了一下 `src/auth.ts`，`verifyToken` 函数（大概第 42 到 58 行）好像用的是旧版 `jsonwebtoken` 的接口。一个办法是升级这个包，然后重写这个函数。改完之后，最好跑一下登录相关的测试，确认没有改坏。顺便说一下，你也可以整体检查一下依赖版本。希望对你有帮助！有问题随时问我。

</td>

<td width="50%">

## 之后

> 改 `src/auth.ts:42` 的 token 校验。
>
> 1. 打开 `src/auth.ts`
> 2. 用下面的代码替换 `verifyToken`（第 42–58 行）
> 3. 运行 `npm test -- auth.spec.ts`
>
> 下一步：测试失败的话，把第一行报错贴过来。

</td>
</tr>
</table>

## 规则

10 条。全文在 [SKILL.md](./skills/shuorenhua/SKILL.md)。

1. 第一句就是下一步动作。
2. 多步骤就编号。
3. 结尾给一个具体的下一步。
4. 不跑题。
5. 每轮都重申进度。
6. 时间估计要具体（几分钟，而不是"一会儿"）。
7. 让完成的成果看得见。
8. 报错就事论事。
9. 列表最多 5 项。
10. 不铺垫，不总结，不客套收尾。

## 开关

- 开启：输入 `/shuorenhua`（Codex 里是 `$shuorenhua`），或者说"说人话模式"。
- 关闭：说"关闭说人话"或"正常模式"。
- 想一直开着：把 [INSTALL.md](INSTALL.md#一直开着可选) 里那段规则粘进 `CLAUDE.md` 或 `AGENTS.md`。

## 改成你自己的

Fork 之后改 `skills/shuorenhua/SKILL.md`，再装你自己的版本：

```bash
claude plugin uninstall shuorenhua
claude plugin marketplace remove shuorenhua
claude plugin marketplace add <你的用户名>/shuorenhua
claude plugin install shuorenhua@shuorenhua
```

重启编程助手，再输入 `/shuorenhua`。

## 许可

[MIT](LICENSE)。

如果它让你少划过一句"好问题！"，点个 ⭐。
