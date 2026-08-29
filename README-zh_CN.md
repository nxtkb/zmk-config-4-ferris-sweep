# NXTKB Ferris Sweep ZMK 配置

[![固件构建](https://img.shields.io/github/actions/workflow/status/nxtkb/zmk-config-4-ferris-sweep/build.yml?branch=main&label=firmware%20build&style=flat-square)](https://github.com/nxtkb/zmk-config-4-ferris-sweep/actions/workflows/build.yml)
[![文档状态](https://img.shields.io/website?url=https%3A%2F%2Fnxtkb.com%2Fzh%2Fdocs%2Fsetup%2Fkeymap%2Fferris-sweep-keymap%2F&label=docs&up_message=online&up_color=2f6f6f&down_message=offline&down_color=8b1e3f&style=flat-square)](https://nxtkb.com/zh/docs/setup/keymap/ferris-sweep-keymap/)
[![键位源码](https://img.shields.io/badge/keymap-cradio.keymap-5f6fbf?style=flat-square)](./config/cradio.keymap)
[![ZMK 配置](https://img.shields.io/badge/ZMK-cradio.conf-6b7280?style=flat-square)](./config/cradio.conf)
[![ZMK Studio](https://img.shields.io/badge/ZMK-Studio-8b5cf6?style=flat-square)](https://zmk.studio/)
[![键鼠测试](https://img.shields.io/website?url=https%3A%2F%2Finput-test.nxtkb.com%2F&label=input%20tester&up_message=online&up_color=2f6f6f&down_message=offline&down_color=8b1e3f&style=flat-square)](https://input-test.nxtkb.com/)

中文 | [English](./README.md)

这个仓库保存 NXTKB Ferris Sweep 的 ZMK 固件配置。它基于
[Sweep](https://github.com/davidphilipbarr/Sweep) 布局，使用
[ZMK](https://github.com/zmkfirmware/zmk) 构建，并在固件支持时可通过
[ZMK Studio](https://zmk.studio/) 实时改键。需要查看源码、fork 配置或
构建固件时，从这里开始；上手、刷写、键位图和日常使用说明，优先看 NXTKB
官方文档。

## 官方文档

- [入门指南](https://nxtkb.com/zh/docs/setup/)
- [Ferris Sweep 键位映射](https://nxtkb.com/zh/docs/setup/keymap/ferris-sweep-keymap/)
- [Ferris Sweep 配置文件](https://nxtkb.com/zh/docs/firmware/ferris-sweep-configuration/)
- [如何更新键位映射](https://nxtkb.com/zh/docs/setup/keymap/how-to-update-keymaps/)
- [如何刷写固件](https://nxtkb.com/zh/docs/firmware/how-to-flash-a-firmware/)
- [键鼠测试](https://nxtkb.com/zh/docs/setup/keymap/input-tester/)
- [在 Ferris Sweep 上使用 Codex Micro](https://nxtkb.com/zh/blog/codex-micro-chatgpt-protocol/)

英文文档也可直接访问：

- [Getting Started](https://nxtkb.com/docs/setup/)
- [Ferris Sweep Keymap](https://nxtkb.com/docs/setup/keymap/ferris-sweep-keymap/)
- [Ferris Sweep Configuration](https://nxtkb.com/docs/firmware/ferris-sweep-configuration/)

## 仓库结构

- `config/cradio.keymap`：层、按键绑定、本位行修饰键、条件三层、鼠标层、
  Boot 键、软关机行为和 ZMK Studio 解锁。
- `config/cradio.conf`：这个键盘的 ZMK 配置选项。
- `build.yaml`：GitHub Actions 固件构建矩阵。
- `.github/workflows/build.yml`：复用 ZMK 用户配置构建流程的固件构建工作流。

## 固定依赖

[![ZMK revision](https://img.shields.io/badge/zmk-b66b8b4e-5f6fbf?style=flat-square)](https://github.com/nxtkb/zmk/tree/b66b8b4e07655d16c01d14bfa06e2f7f6c46025f)
[![zmk-behavior-report revision](https://img.shields.io/badge/zmk--behavior--report-476f43da-2f6f6f?style=flat-square)](https://github.com/nxtkb/zmk-behavior-report/tree/476f43da1f98b4a6150c9c0e499a257bd64a29a0)

固件构建依赖由 `config/west.yml` 固定：

| 项目 | 远端 | Revision |
| :--- | :--- | :--- |
| `zmk` | `nxtkb/zmk` | `b66b8b4e07655d16c01d14bfa06e2f7f6c46025f` |
| `zmk-behavior-report` | `nxtkb/zmk-behavior-report` | `476f43da1f98b4a6150c9c0e499a257bd64a29a0` |

## 固件和改键流程

如果要做长期保留的配置修改：

1. Fork 这个仓库。
2. 修改 `config/cradio.keymap` 或 `config/cradio.conf`。
3. 等待 GitHub Actions 构建固件。
4. 下载构建产物，把对应 UF2 固件刷到对应半边键盘。

如果当前固件支持 ZMK Studio，日常键位的快速调整优先使用
[ZMK Studio](https://zmk.studio/)。
完整取舍请看官网的
[如何更新键位映射](https://nxtkb.com/zh/docs/setup/keymap/how-to-update-keymaps/)。

### Codex Micro 构建

公开的 `zmk-feature-codex-micro` 模块已经以固定 commit 加入 `config/west.yml`。默认
GitHub Actions workflow 会为左手构建同时支持 USB 和蓝牙 Codex 的固件，右手仍构建为
普通 split peripheral。

固定的 `nxtkb/zmk` revision 已包含模块所需的 USB HID interrupt-OUT 支持，不再需要
单独应用 patch。发布固件会启用模块的最小兼容身份，只修改 USB VID/PID 和蓝牙 PnP
VID/PID；用户可见的键盘名称仍可配置。这些标识符不代表 OpenAI 认证，且 ChatGPT
未公开的发现机制未来可能变化。

## 键位摘要

完整键位图和逐层说明请看官网：

- [Ferris Sweep 键位映射](https://nxtkb.com/zh/docs/setup/keymap/ferris-sweep-keymap/)
- [Ferris Sweep Keymap](https://nxtkb.com/docs/setup/keymap/ferris-sweep-keymap/)
- [在 keymap-drawer 查看最新键位](https://keymap-drawer.streamlit.app/?zmk_url=https%3A%2F%2Fgithub.com%2Fnxtkb%2Fzmk-config-4-ferris-sweep%2Fblob%2Fmain%2Fconfig%2Fcradio.keymap)

当前默认层级：

- 默认层：输入字符，并在本位行放置修饰键。
- 数字和导航层：按住右侧 `TAB` 层键进入。
- 符号层：按住左侧 `TAB` 层键进入。
- 功能层：同时按住左右 `TAB` 层键进入，用于蓝牙档位、输出切换、
  进入 Codex 层、ZMK Studio 解锁和软关机。
- 鼠标层：在符号层按 `SPACE` 进入，按 `P` 或 `Q` 退出。
- Codex 层：在功能层按 `I` 进入；`Q`–`Y` 对应 Agent 1–6，
  `A`/`S`/`D`/`F` 对应批准/分叉/拒绝/Fast，`H`/`J` 对应语音/发送，
  按 `P` 退出。

## Bootloader 和刷写提示

进入 bootloader 可任选一种方法：

1. 键盘已连接时，按键位里的 `Boot` 键。
2. 双击 reset 按钮。
3. 如果 reset 按钮不可用，短接 `RST` 和 `GND` 两次。

固件文件名通常会标明目标：

- `left`：左手固件。
- `right`：右手固件。
- `reset`：清除蓝牙配对信息的 reset 固件。

如果只改了按键或键盘名称，通常只需要刷左手。如果改到分体行为、板级配置或
右手行为，也要刷受影响的半边。刷写前请先看官网的
[如何刷写固件](https://nxtkb.com/zh/docs/firmware/how-to-flash-a-firmware/)。
