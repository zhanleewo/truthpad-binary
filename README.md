# TruthPad binaries

安装包与插件包的**发布仓库**（源码不在这里，见私有仓库 `zhanleewo/truthpad`）。

Release 里放三类东西：

| 内容 | 说明 |
| --- | --- |
| `TruthPad-Setup-Beta.exe` | **公测渠道**安装包：pdf / wsl / imageviewer / browser 四个插件，装好即用 |
| `TruthPad-Setup-GA.exe` | **正式渠道**安装包：只有 imageviewer + wsl（不含浏览器插件；wsl 装好后默认禁用） |
| `<插件id>.zip` × 8 | 插件独立包（aiagent / browser / imageviewer / netdisk / pdf / sample / videoplayer / wsl） |
| `sources.json`、`index.json` | 插件源索引（`sources.json` 与 `index.json` 内容相同） |

## 安装

1. 下载渠道安装包（Beta 功能全、GA 最精简），运行即可 —— 不写注册表以外的地方，卸载用安装目录里的 `unins.exe`。
2. 每个 `.exe` 旁边的 `.sha256` 是对应校验值（`sha256sum -c` 或 `Get-FileHash` 对一下）。

## 插件包的两种用法

- **应用内安装**：把 `sources.json` 里的 `archive` 字段当成文件名的相对地址（客户端按"索引所在目录 + archive"拼下载地址），
  放进「插件」页的源地址即可在线安装/更新。
- **离线安装**：直接下载 `<插件id>.zip`，在「插件」页里选「从本地 zip 安装」。

安装包与插件包均为 **Windows x64**；主程序是纯 Win32 单 exe，不依赖 Node/npm。

---

*TruthPad — a lightweight, Windows-native editor (C++20 / pure Win32). Installers and plugin
packages are published here as release assets; the source lives in a private repository.*
