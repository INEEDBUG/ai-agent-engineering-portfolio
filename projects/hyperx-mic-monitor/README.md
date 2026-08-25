# HyperX Cloud II 麦克风被动诊断与监控

## Problem

游戏过程中 USB 麦克风偶发无声，但播放仍正常且故障难以复现。需要在不占用录音流、不抢焦点、不自动修复的前提下，区分设备掉线、端点变化和内部采集路径停滞。

## Design

- 使用 `IAudioMeterInformation` 读取峰值，不创建录音流。
- 使用 `IAudioSessionManager2` 记录真实捕获会话，而不是根据进程存在推断占用。
- 订阅 Windows 音频与设备事件，并以只读共享方式监听可用 HID 输入。
- 采用 750 ms 采样、60 分钟滚动日志和候选事件前后各 60 秒证据保全。
- 不执行设备重启、驱动更改或自动修复。

## Verified outcomes

- 游戏进程运行 45 秒实测：总 CPU 约 0.0058%，工作集约 34.9 MB，日志增长约 44.5 KB/分钟。
- 能识别真实音频会话状态，未把仅有游戏进程存在误判为麦克风正在使用。
- 故障窗口未发现设备重新枚举或音频服务重启；该证据支持采集路径停滞方向，但不足以证明固件故障。

## Source

Public source: [INEEDBUG/hyperx-cloud-ii-mic-monitor](https://github.com/INEEDBUG/hyperx-cloud-ii-mic-monitor)

Release: [v1.0.0](https://github.com/INEEDBUG/hyperx-cloud-ii-mic-monitor/releases/tag/v1.0.0)

Raw logs and workstation-specific device topology are intentionally excluded.
