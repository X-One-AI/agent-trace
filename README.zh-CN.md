# agent-trace

语言： [English](./README.md) | 中文

> 这是一个决策仓库，不是活跃产品构建。它用于吸收、拒绝，或把想法路由回已发布的 Safe Agent Operations 工具。

泛 AI agent tracing 暂缓；只保留 failure packet 这个差异化切口。

## 状态

`v0.1.0` - deferred tracing decision 和 failure-packet evidence wedge。

## 目的

Avoid competing head-on with established tracing and observability platforms.

## 第一生产化表面

Decision log：防止 scope creep，并只保留对 failure packet 有帮助的 trace evidence。

v0.1.0 明确不发布 tracing backend、dashboard 或 CLI。

## 必要证据

- deferred rationale
- competition notes
- allowed evidence wedge
- delete-or-merge review cadence

## 决策

泛 agent tracing 暂缓。只保留能够增强 `agent-failure-packet` 的 packet-shaped trace evidence。

新的 trace 想法应分类为 `move-to-agent-failure-packet`、`watch` 或 `reject`。

## 非目标

- not a dashboard
- not a tracing backend
- not a Langfuse/Phoenix/LangSmith clone

## OPT 运行模型

本项目通过 [ops/opt-overlay.md](./ops/opt-overlay.md) 引用共享 One Person Team 工作流。项目自己的约束放在 [ops/constraints](./ops/constraints)，可演进 skill 放在 [ops/skills](./ops/skills)。

## 暂缺输入

需要用户或真实世界数据补充的内容记录在 `../x-one-skipped-inputs.md`，不阻塞基础建设。

## 文档

- [产品基础](./docs/product-foundation.md)
- [Defer Decision](./docs/defer-decision.md)
- [Evidence Wedge](./docs/evidence-wedge.md)
- [Review Cadence](./docs/review-cadence.md)
- [OPT Overlay](./ops/opt-overlay.md)
- [生产约束](./ops/constraints/production.md)
- [主入口约束](./ops/constraints/main-entry.md)
- [Skill 演进](./ops/skills/evolution.md)
