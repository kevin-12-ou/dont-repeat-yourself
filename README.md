# Don't Repeat Yourself

[简体中文](README.zh-CN.md) | [Skill instructions](SKILL.md) | [Maintainer: kevin-12-ou](https://github.com/kevin-12-ou)

**An AI agent skill for saving verified coding solutions as searchable recipes and adapting them to future projects.**

A working script and its hard-won constraints often disappear into a long chat. Rebuilding them later wastes effort and can repeat the same failures.

This is an **Agent Skill: instructions and reference material for an AI assistant**, not a hosted service or an autonomous program. The package contains no installation hooks, application runtime, models, background services, or credentials; its Python script is only for development-time package validation. The assistant still operates under its host permissions and the user's authorization.

## When to use it

- Search a short index before loading only the relevant recipes.
- Check current code, versions, prerequisites, and limits before reuse.
- Capture final artifacts and evidence rather than reconstructing code from memory.
- Keep credentials, personal data, and machine-specific values out of reusable artifacts.

## Install

Use Git and an assistant that supports Agent Skills. The optional Skills CLI below also requires Node.js/npm and is a separate executable tool to review before running. This skill itself needs no API key, database, or paid account; your chosen AI assistant may have its own costs.

```sh
npx skills add kevin-12-ou/dont-repeat-yourself --skill dont-repeat-yourself
```

Choose the agent and scope in the installer. For a project-local Codex installation, with copied files rather than symlinks:

```sh
npx skills add kevin-12-ou/dont-repeat-yourself --skill dont-repeat-yourself --agent codex --copy
```

Manual option: copy the complete repository into a skill directory named `dont-repeat-yourself`, such as `.agents/skills/dont-repeat-yourself/`, where supported by your assistant. Keep `SKILL.md` and its referenced files together; follow your client's skill-directory documentation.

## Example prompts

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

Explicitly naming the skill helps make intent clear. Automatic selection depends on the model and client and is not guaranteed. The package follows the [Agent Skills specification](https://agentskills.io/specification); clients such as Codex and Claude Code can read this format, but equivalent behavior across every client is not claimed. Core instructions are primarily English; this English README provides discovery and usage context.

## Boundaries and data

The public package starts with an empty library. It is a workflow, not cloud memory or automatic cross-device synchronization. Saving experience does not authorize publishing it or changing global agent instructions.

No private project history is bundled. File access, network requests, commands, and edits depend on the task and the assistant's tools. A text skill is not an isolation boundary or a mandatory security interceptor.


Personal recipe files are ignored by Git, but the starter `library/INDEX.md` is tracked. Do not commit personal index entries or publish a populated library. Back up your private library before updates. The public validator intentionally rejects a populated index.

## Maintenance and feedback

For Skills CLI installs, `npx skills check` checks for updates and `npx skills update` updates installed skills. Review changes first. Disable the skill in your client, or move its installed directory out of discovery, to stop using it. Back up any personal additions before updating or removing it, especially a recipe library.

Report a sanitized example in [Issues](https://github.com/kevin-12-ou/dont-repeat-yourself/issues). See [CONTRIBUTING.md](CONTRIBUTING.md) and [VALIDATION.md](VALIDATION.md) for contribution and validation boundaries.

## Related skills by kevin-12-ou

- [Concept to Action Coach](https://github.com/kevin-12-ou/concept-to-action-coach) — An AI agent skill for explaining technical concepts to beginners and turning understanding into a small, verifiable action.
- [Deploy Onboarding Guide](https://github.com/kevin-12-ou/deploy-onboarding-guide) — A Chinese-first AI agent skill for assessing open-source software before installation and explaining setup, permissions, costs, and first use.
- [Release Migration Parity](https://github.com/kevin-12-ou/release-migration-parity) — An AI agent skill for preserving accepted UI, behavior, and data semantics when releasing an app or migrating it to another platform.

Maintained by [kevin-12-ou](https://github.com/kevin-12-ou). Developed from personal AI-assisted workflows. Licensed under [MIT](LICENSE); see [NOTICE.md](NOTICE.md) for provenance.
