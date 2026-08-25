# AI Agent & Systems Engineering Portfolio

面向 AI Agent 应用工程、系统工程与可靠性交付岗位的脱敏项目作品集。这里展示问题定义、架构决策、工程边界和可复核结果；不上传家庭网络配置、真实运行日志、访问凭据、设备唯一标识或私有产品源码。

## Projects

| 项目 | 方向 | 可公开内容 |
|---|---|---|
| [多节点 AI Agent 与可恢复长期记忆平台](projects/ai-agent-memory-platform/README.md) | Agent Runtime / Memory / Recovery | 脱敏架构、恢复结果、上游贡献 |
| [MaxGameStudio 本地游戏数据分析桌面产品](projects/maxgamestudio/README.md) | Desktop AI / Product Delivery | 产品与架构案例；源码私有 |
| [CW701 录像安全合并与存储恢复](projects/cw701-video-safety/README.md) | Go / Docker / FFmpeg / Storage | 安全设计与验证案例；真实录像和配置不公开 |
| [HyperX Cloud II 麦克风被动诊断与监控](projects/hyperx-mic-monitor/README.md) | Windows / Core Audio / Diagnostics | 案例页与独立公开源码仓库 |
| [旧版 Excel 工作表保护离线处理工具](projects/legacy-xls-tool/README.md) | PowerShell / OLE / BIFF | 授权场景下的离线工具案例 |
| [Linux / FnOS / iStoreOS / VPS 基础设施治理](projects/linux-fnos-infrastructure/README.md) | Linux / Docker / NAS / Network | 脱敏运维架构、恢复与验收方法 |

## Engineering principles

- Evidence before diagnosis: separate verified facts, hypotheses and unresolved state.
- Reversible delivery: preserve originals, create rollback points and verify the user-facing result.
- Local-first data handling: keep private data and diagnostic evidence on the user's device.
- Resource-aware design: prefer lightweight storage and passive observation on constrained nodes.
- Honest boundaries: an upstream review, a partial recovery or an unverified hypothesis is described as such.

## Public evidence policy

公开材料只保留招聘和技术交流需要的工程信息。以下内容一律排除：密码、Token、OAuth 材料、私钥、公网或内网地址、家庭拓扑、设备序列号、用户目录、真实聊天内容、原始摄像头录像、未脱敏日志及第三方个人数据。

This repository contains sanitized engineering case studies. Product names belong to their respective owners; no affiliation or endorsement is implied.
