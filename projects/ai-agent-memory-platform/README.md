# 多节点 AI Agent 与可恢复长期记忆平台

## Problem

个人 AI Agent 在跨设备、跨会话长期运行时，容易出现上下文膨胀、事实重复、节点身份混淆、配置漂移和重装后历史丢失。项目目标是在资源受限设备与 Windows 工作站之间建立可检索、可恢复、可审计的 Agent 工作环境。

## Architecture

- 常驻上下文保存稳定身份、规则和当前工作边界。
- SQLite + WAL/FTS5 保存结构化事实，并结合去重与分类治理。
- 脱敏 Git 快照保存可恢复配置与知识资产。
- 会话检索用于按需回溯历史，而不是把全部历史永久注入提示词。
- x86 边缘节点、ARM 低功耗节点、Windows 工作站和 VPS 按职责隔离身份与备份边界。

## Responsibilities

- 设计记忆分层、迁移阈值、定时压缩和恢复验收规则。
- 集成 OpenClaw、Hermes Agent、Codex、模型路由、工具调用与子 Agent 编排。
- 治理多渠道入口、节点身份、配置备份、日志审计和敏感信息脱敏。
- 对状态数据库损坏、配置 Schema 不兼容和事件循环阻塞开展根因分析。

## Verified outcomes

- 从 15 份历史备份中恢复并校验 124 个会话、6,617 条消息和 163 条长期事实。
- 恢复 10 个技能、3 个定时任务、11 个脚本和 2 个补丁，并以 SQLite 完整性检查验收。
- 将常驻 Memory 从 2,702 字符压缩至 1,556 字符，并迁移 17 条可结构化事实。
- 在 2 GB ARM 节点上以 SQLite/WAL/FTS5 维护 43 条事实，连续 3 次每日压缩任务成功。

## Open-source contribution

- [Hermes Agent PR #44156](https://github.com/NousResearch/hermes-agent/pull/44156): a focused prototype for reducing unsafe cross-session context injection. Maintainer review confirmed the underlying risk; the patch was not directly merged because the upstream boundary required broader redesign.
- [Hermes Agent issue #44094](https://github.com/NousResearch/hermes-agent/issues/44094): root-cause tracking and upstream coordination.

## Source and release

- Source: [INEEDBUG/agent-memory-recovery-toolkit](https://github.com/INEEDBUG/agent-memory-recovery-toolkit)
- Release: [v1.0.0](https://github.com/INEEDBUG/agent-memory-recovery-toolkit/releases/tag/v1.0.0)

The public implementation contains the sanitized SQLite/FTS schema, migration, audit, snapshot and restore tooling, plus automated recovery tests.

## Developers

INEEDBUG (product owner), OpenAI Codex (AI development collaborator), and Hermes Agent (AI development collaborator).

## Public boundary

No prompts, chat contents, credentials, channel identifiers, host addresses, configuration snapshots or raw databases are included in this repository.
