# 旧版 Excel 工作表保护离线处理工具

## Authorized use case

面向用户拥有并获授权处理的旧版 `.xls` 文件，提供无需安装 Excel、无需联网的工作表保护处理能力。项目明确区分工作表保护、文件打开密码和现代 `.xlsx` 加密，不声称绕过文件加密。

## Design

- 直接解析 OLE/BIFF 中的 `PROTECT` 与 `PASSWORD` 记录。
- PowerShell 5.1 + WinForms 提供图形界面和命令行回退。
- 支持单文件、文件夹、递归批处理和拖放入口。
- 使用唯一临时输出名、写后回读校验与原文件保留策略。

## Verified outcomes

- 在包含 4 个工作表的授权样本中，仅修改副本内 12 字节。
- 复核后活动保护记录为 0，原文件 SHA-256 保持不变。
- v1.2.0 便携包完成图形界面、批处理、重复文件名、失败回滚和写后验证测试。

## Public boundary

No user spreadsheets, extracted workbook contents or password material are included. Source code remains private while the safety model and supported boundary are documented here.
