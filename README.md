# AI Agent & Systems Engineering Portfolio

面向 AI Agent 应用工程、系统工程与可靠性交付岗位的脱敏项目作品集。这里展示问题定义、架构决策、工程边界和可复核结果；不上传家庭网络配置、真实运行日志、访问凭据、设备唯一标识或私有产品源码。

## Projects

| 项目 | 方向 | 源码 | Release |
|---|---|---|---|
| [多节点 AI Agent 与可恢复长期记忆平台](projects/ai-agent-memory-platform/README.md) | Agent Runtime / Memory / Recovery | [agent-memory-recovery-toolkit](https://github.com/INEEDBUG/agent-memory-recovery-toolkit) | [v1.0.0](https://github.com/INEEDBUG/agent-memory-recovery-toolkit/releases/tag/v1.0.0) |
| [MaxGameStudio 本地游戏数据分析桌面产品](projects/maxgamestudio/README.md) | Desktop AI / Product Delivery | [MaxGameStudio](https://github.com/INEEDBUG/MaxGameStudio) | [RC 2.5.14-rc.58](https://github.com/INEEDBUG/MaxGameStudio/releases/tag/rc-2.5.14-rc.58) |
| [CW701 录像安全合并与存储恢复](projects/cw701-video-safety/README.md) | Go / Docker / FFmpeg / Storage | [cw701-video-merge-public](https://github.com/INEEDBUG/cw701-video-merge-public) | [v2.0.0](https://github.com/INEEDBUG/cw701-video-merge-public/releases/tag/v2.0.0) |
| [HyperX Cloud II 麦克风被动诊断与监控](projects/hyperx-mic-monitor/README.md) | Windows / Core Audio / Diagnostics | [hyperx-cloud-ii-mic-monitor](https://github.com/INEEDBUG/hyperx-cloud-ii-mic-monitor) | [v1.0.0](https://github.com/INEEDBUG/hyperx-cloud-ii-mic-monitor/releases/tag/v1.0.0) |
| [旧版 Excel 工作表保护离线处理工具](projects/legacy-xls-tool/README.md) | PowerShell / OLE / BIFF | [legacy-xls-worksheet-tool](https://github.com/INEEDBUG/legacy-xls-worksheet-tool) | [v1.2.0](https://github.com/INEEDBUG/legacy-xls-worksheet-tool/releases/tag/v1.2.0) |
| [Linux / FnOS / iStoreOS / VPS 基础设施治理](projects/linux-fnos-infrastructure/README.md) | Linux / Docker / NAS / Network | [linux-fnos-ops-toolkit](https://github.com/INEEDBUG/linux-fnos-ops-toolkit) | [v1.0.0](https://github.com/INEEDBUG/linux-fnos-ops-toolkit/releases/tag/v1.0.0) |

## Engineering principles

- Evidence before diagnosis: separate verified facts, hypotheses and unresolved state.
- Reversible delivery: preserve originals, create rollback points and verify the user-facing result.
- Local-first data handling: keep private data and diagnostic evidence on the user's device.
- Resource-aware design: prefer lightweight storage and passive observation on constrained nodes.
- Honest boundaries: an upstream review, a partial recovery or an unverified hypothesis is described as such.

## Public evidence policy

公开材料只保留招聘和技术交流需要的工程信息。以下内容一律排除：密码、Token、OAuth 材料、私钥、公网或内网地址、家庭拓扑、设备序列号、用户目录、真实聊天内容、原始摄像头录像、未脱敏日志及第三方个人数据。

This repository contains sanitized engineering case studies. Product names belong to their respective owners; no affiliation or endorsement is implied.
