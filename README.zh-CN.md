# 成功方案复用与经验库 · dont-repeat-yourself

[English](README.md) | [技能正文](SKILL.md) | [维护者：kevin-12-ou](https://github.com/kevin-12-ou)

脚本已经跑通、坑也踩过了，换个项目却又从头找。这个技能把成功结果整理成可搜索的小配方，并在下次使用前核验适用条件。

这是给 AI 编程助手读取的 **Agent Skill（指令与参考材料）**。包内不包含后台服务、安装执行钩子或模型；Python 脚本仅用于开发时检查包结构；安装后由助手按需读取，实际操作仍受宿主工具权限和用户授权约束。

## 能帮你做什么

- 先查短索引，只读与任务相关的配方。
- 复用前检查当前代码、版本、前提和已知限制。
- 保存实际最终文件与验证依据，不凭记忆重建成“已测试版本”。
- 记录失败路线和替换点；排除密钥、个人数据和私人路径。

## 安装

需要 Git 和支持 Agent Skills 的 AI 助手。使用下面的 Skills CLI 命令还需要 Node.js/npm；CLI 是外部安装工具，运行前请自行审阅。安装本包不需要 API Key、数据库或付费账号，所用 AI 助手本身可能收费。

```sh
npx skills add kevin-12-ou/dont-repeat-yourself --skill dont-repeat-yourself
```

CLI 会让你选择助手和安装范围。建议先装到测试项目中检查效果。以下是 Codex 的项目级安装示例，不带 `--global`：

```sh
npx skills add kevin-12-ou/dont-repeat-yourself --skill dont-repeat-yourself --agent codex --copy
```

手动安装：下载本仓库，将完整目录保留为 `dont-repeat-yourself`，放到助手支持的技能目录中，例如 `.agents/skills/dont-repeat-yourself/`。保留参考文件，不能只复制 README；以助手文档为准。

## 直接这样问

```text
Use $dont-repeat-yourself. This script worked and I want to reuse it. Save the final file, prerequisites, evidence, and pitfalls as a recipe; remove private values.
```

```text
用 $dont-repeat-yourself。这个脚本跑通了，下次还要复用。保存最终文件、前提、验证依据和踩坑，去掉私人信息。
```

```text
Use $dont-repeat-yourself. Before implementing this CSV import, check whether my recipe library contains a relevant solution and verify that it fits this project.
```

```text
用 $dont-repeat-yourself。开始做这个 CSV 导入前，先查经验库有没有能复用的方案，再核对当前项目是否适用。
```

显式点名更清楚；自动选择由模型和客户端决定，不保证每次命中。本包采用通用 [Agent Skills 格式](https://agentskills.io/specification)，在 Codex、Claude Code 等支持该格式的工具中可供读取；未宣称所有客户端的实际行为均已测试。技能正文以英文为主。

## 边界与数据

公开包的经验库是空的，不带维护者的个人项目记录。它不是云端记忆或自动跨设备同步；保存经验也不代表允许公开发布或修改全局规则。

包内没有凭据或个人项目记录。是否读取项目、写文件、联网或执行命令，取决于任务和助手权限；公开技能本身不会提供隔离或强制拦截。


配方文件已加入 Git 忽略规则，但初始 `library/INDEX.md` 仍是受版本控制的文件。不要提交个人索引条目或公开已有经验库；更新前备份。公开包检查会拒绝带个人条目的索引。

## 更新、停用与贡献

通过 Skills CLI 安装时可用 `npx skills check` 检查更新、`npx skills update` 更新已安装技能；更新前审阅差异。停用可在助手设置中禁用，或移走安装的技能目录；先备份自己新增的内容。`dont-repeat-yourself` 用户尤其应保留自己的经验库。

问题和改进建议请提交到 [Issues](https://github.com/kevin-12-ou/dont-repeat-yourself/issues)，提供去除隐私的最小例子。维护说明见 [CONTRIBUTING.md](CONTRIBUTING.md)，公开包检查见 [VALIDATION.md](VALIDATION.md)。

## 同一维护者的其他技能

- [从概念到行动教练](https://github.com/kevin-12-ou/concept-to-action-coach) — 听过术语，也能复述定义，但仍不知道什么时候需要它、该怎么开始。这个技能把解释接到一个能完成、能验收的小行动上。
- [开源项目安装评估与上手指南](https://github.com/kevin-12-ou/deploy-onboarding-guide) — 只说“部署好了”不够。用户还需要知道它具体干什么、需不需要 API 或付费账号、会改哪里，以及第一次怎么用。
- [上线与迁移一致性](https://github.com/kevin-12-ou/release-migration-parity) — 本地验收没问题，上线后弹窗样式却变了，旧新版数据不互通；或者迁移到小程序时悄悄漏掉原有功能。这个技能围绕已验收体验做对照。

由 [kevin-12-ou](https://github.com/kevin-12-ou) 维护，整理自个人 AI 辅助工作流。采用 [MIT](LICENSE) 许可；来源说明见 [NOTICE.md](NOTICE.md)。
