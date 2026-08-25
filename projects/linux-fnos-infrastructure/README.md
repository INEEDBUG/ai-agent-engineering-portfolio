# Linux / FnOS / iStoreOS / VPS 基础设施治理

## Scope

长期维护 x86 N100/FnOS NAS、ARM N1/iStoreOS 边缘节点和 Linux VPS，覆盖 Docker 服务、网络与 DNS、存储、监控、安全基线、Agent Runtime 和故障恢复。关键约束是不因排障中断现有家庭服务或破坏原始数据。

## Responsibilities

- Linux 与 Docker 服务部署、升级、日志审计、资源约束和回滚。
- FnOS NAS 上的 SMB、摄像头录像、USB bridge、RAID/LVM/ext4 和容器工作负载维护。
- iStoreOS 上的 DHCP/DNS/旁路网关角色治理、代理启动时序和低内存 Agent 运行。
- VPS 密钥访问恢复、防火墙默认拒绝策略、Fail2ban 与关键服务核验。
- AdGuard Home、Docker DNS 与客户端解析链路的无中断变更。

## Representative incidents

### Storage recovery

设备名发生漂移后按 RAID/LVM/文件系统 UUID 重新识别链路，先备份元数据，再执行离线文件系统检查，并用同步写入、Direct I/O 与 SHA-256 回读验证真实 I/O。发现新的 I/O error 时停止扩大部署范围。

### DHCP and DNS governance

定位两个节点同时发放 DHCP 导致的地址冲突，关闭边缘节点 DHCP 但保留所需 DNS/代理能力；通过监听端口、客户端租约、DNS 解析和关键服务访问完成重启后验收。

### Lightweight Agent operations

在 2 GB ARM/iStoreOS 节点上运行 Hermes Agent 与本地 SQLite/FTS5 记忆；部署双分钟级 watchdog，在约 13 小时日志窗口内观测 399 次调度、0 次异常接管，容器 `RestartCount=0`、`OOMKilled=false`。

## Operating model

- Read-only inspection before mutation.
- Explicit rollback point before critical changes.
- Device identification by stable IDs rather than drive letters.
- User-facing read/write and service-availability verification after change.
- Unresolved state is retained instead of being reported as success.

## Public boundary

No IP addresses, domain names, share names, hostnames, credentials, topology diagrams, filesystem UUIDs, private configuration or raw logs are included.
