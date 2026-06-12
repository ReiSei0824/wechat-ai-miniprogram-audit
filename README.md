# 微信 AI 小程序接入审查 · WeChat AI Mini Program Audit

Reusable Codex skill for reviewing whether a WeChat mini program is ready to add AI features, and for turning that review into a practical implementation plan.

## What It Does

| # | Capability | Description |
|---|---|---|
| 1 | Project inventory | Reads mini program structure such as `project.config.json`, `app.json`, pages, components, cloud functions, and API wrappers. |
| 2 | Access-mode choice | Compares page-level AI entry, cloud-function proxy, own API gateway, AI customer service, AI search, and Agent workflow patterns. |
| 3 | Compliance pass | Flags AIGC labeling, personal information, model hallucination, content safety, logging, and review concerns. |
| 4 | Execution plan | Produces file-level tasks, acceptance criteria, fallback logic, rollout steps, and manual QA scripts. |

## Trigger Phrases

- 帮我看看这个小程序怎么接微信 AI
- 微信 AI 小程序接入审查
- 小程序 AI 化改造方案
- Audit this WeChat mini program for AI readiness
- WeChat AI mini program rollout plan

## Workflow

1. Clarify the AI use case, audience, platform constraints, and launch boundary.
2. Inspect the mini program project files or, if no files are supplied, run a structured pre-audit checklist.
3. Choose feasible access modes and describe frontend, backend, auth, cost, and fallback impact.
4. Review compliance and trust risks, especially AIGC labeling, personal data, hallucination, and manual escalation.
5. Generate implementation tasks with file paths, priorities, owners, and acceptance criteria.
6. Produce a final audit report, rollout checklist, and follow-up items.

## Example Output

```markdown
# 微信 AI 小程序接入审查报告

## 结论
- 推荐接入模式：云函数代理
- 当前可行性：中
- 最大风险：模型输出缺少来源提示和人工转接机制

## 实施任务表
| 优先级 | 文件/模块 | 任务 | 验收标准 |
|---|---|---|---|
| P0 | cloudfunctions/aiProxy | 新增模型代理和频控 | 前端不暴露密钥，异常时返回降级文案 |
```

## Scope

This skill does:

- Review existing mini program projects for AI readiness.
- Design a practical AI access pattern for the WeChat ecosystem.
- Produce compliance, rollout, fallback, and QA checklists.

This skill does not:

- Apply for WeChat platform permissions on the user's behalf.
- Bypass platform review or content moderation.
- Replace legal advice for privacy, medical, financial, or regulated scenarios.

## Installation

Place this folder under:

```text
~/.claude/skills/微信AI小程序接入审查（wechat-ai-miniprogram-audit）/
```

The required entry file is:

```text
SKILL.md
```

## 发布说明

建议 GitHub 仓库名：

```text
wechat-ai-miniprogram-audit
```

发布前检查：

- `SKILL.md` frontmatter includes lowercase-hyphen `name`.
- Description clearly states when the skill should trigger.
- README includes bilingual usage, workflow, example output, and scope boundaries.
