# MaxGameStudio 本地游戏数据分析桌面产品

## Problem

为 CS2 玩家提供本地优先的比赛数据分析与训练工作台，在不上传个人比赛数据的前提下完成 Demo 获取、解析、回放和统计，并把安装、升级和异常数据处理纳入产品交付。

## Stack

Python, FastAPI, React, Tauri, SQLite and mature open-source CS2 demo components.

## Responsibilities

- 负责产品定位、需求优先级、技术路线、AI 协作开发与 Windows 交付验收。
- 整合 Demo 获取与解析、比赛列表、二维回放、训练视图和本地统计。
- 建立自动化测试、视觉回归、安装包验收、原位升级和品牌迁移检查。
- 在个人桌面场景以 SQLite 替代重型常驻数据库，降低部署和维护成本。

## Verified outcomes

- 通过 Steam Game Coordinator 校正比赛时间语义，避免旧 Demo 或未知时间被误报为刚结束的比赛。
- 推进至 2.5.14 RC 系列，完成品牌迁移、旧快捷方式清理和原位升级校验。
- 将“元数据已更新”与“用户桌面真实体验已迁移”拆分验收，修复旧品牌残留问题。

## Source and public boundary

Public source: [INEEDBUG/MaxGameStudio](https://github.com/INEEDBUG/MaxGameStudio)

Release: [RC 2.5.14-rc.58](https://github.com/INEEDBUG/MaxGameStudio/releases/tag/rc-2.5.14-rc.58)

The portfolio does not duplicate local release worktrees, game data, Demo files, Steam identifiers, databases, logs, private configuration, access tokens or third-party assets. The case study documents product and engineering decisions without exposing user data.
