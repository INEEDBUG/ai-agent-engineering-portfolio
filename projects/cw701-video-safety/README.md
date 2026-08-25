# CW701 录像安全合并与存储恢复

## Problem

摄像头会持续生成大量分段录像。自动合并必须避免读取仍在写入的目录、覆盖原始录像或在存储异常时扩大损失，同时还要支持失败重试和重复运行。

## Design

- Go 负责递归发现、全路径排序、按日/小时分组和状态管理。
- FFmpeg 执行媒体合并，FFprobe 负责输出校验。
- Docker 以只读输入、非 root、禁用网络和只读根文件系统运行。
- 输出先写入 `.partial.mp4`，通过校验后原子重命名。
- 状态记录提供幂等执行和失败可重试能力。

## Verified outcomes

- 完成单元测试、样本合并、哈希校验、重复运行跳过和受限容器测试。
- 验证工具不会覆盖原始录像，并能够跳过当前仍在写入的目录。
- 对 USB bridge、RAID/LVM/ext4 链路执行按 UUID 识别、元数据备份、离线检查和真实 I/O 回读。
- 当真实 I/O 异常再次出现时停止生产部署，保留原始录像并明确标记应用侧恢复仍待验证。

## Source and release

- Source: [INEEDBUG/cw701-video-merge-public](https://github.com/INEEDBUG/cw701-video-merge-public)
- Release: [v2.0.0](https://github.com/INEEDBUG/cw701-video-merge-public/releases/tag/v2.0.0)

## Developers

INEEDBUG (product owner), OpenAI Codex (AI development collaborator), and Hermes Agent (AI development collaborator).

## Public boundary

No camera footage, NAS paths, share names, IP addresses, filesystem UUIDs, SMART serials or private deployment configuration are published. The public implementation is an independently rewritten, sanitized subset and excludes unlicensed upstream code.
