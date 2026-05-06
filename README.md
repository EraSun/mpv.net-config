# mpv.net 自用配置

个人的 mpv.net 播放器配置，适用于 Windows 11 环境。

## 功能

- **HDR/SDR 色调映射** — bt.2446a / hable 双模式
- **高品质视频缩放** — ewa_lanczos + 去色带 + 缓存
- **缩略图预览** — hover 进度条时显示画面缩略图（thumbfast + osc.lua）
- **批量快捷键** — 画面控制、音频、字幕、截图、均衡器一键操作
- **暂停自动取消置顶** — ontop-playback 脚本

## 文件说明

| 文件 | 用途 |
|------|------|
| `mpv.conf` | 核心播放设置（渲染器、HDR、缩放、音频） |
| `mpvnet.conf` | mpv.net 程序设置 |
| `input.conf` | 快捷键绑定 + 右键菜单 |
| `scripts/osc.lua` | 进度条 OSC + 缩略图集成（thumbfast 补丁版） |
| `scripts/thumbfast.lua` | 缩略图生成引擎 |
| `scripts/ontop-playback.lua` | 暂停时自动取消置顶 |
| `script-opts/thumbfast.conf` | 缩略图参数（路径、尺寸、解码） |

## 安装

将仓库所有文件复制到 `%APPDATA%\mpv.net\`：

```powershell
Copy-Item -Recurse -Force .\* "$env:APPDATA\mpv.net\"
```

## 前置条件

- [mpv.net](https://github.com/mpvnet-player/mpv.net) 最新版
- [mpv](https://mpv.io/) 独立安装（thumbfast 子进程需要 mpv.exe）
  - 推荐通过 [Scoop](https://scoop.sh/) 安装：`scoop install mpv`
  - 确认 `script-opts/thumbfast.conf` 中 `mpv_path` 指向正确路径

## 环境

- OS: Windows 11
- 显示器: HDR 1600nit 峰值 / 700nit 持续
- mpv.net 版本: 7.x+
- mpv 版本: 0.41.0 (via Scoop)
