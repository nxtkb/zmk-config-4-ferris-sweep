# NXTKB Ferris Sweep ZMK 配置

[![Firmware Build](https://img.shields.io/github/actions/workflow/status/nxtkb/zmk-config-4-ferris-sweep/build.yml?branch=main&label=firmware%20build&style=flat-square)](https://github.com/nxtkb/zmk-config-4-ferris-sweep/actions/workflows/build.yml)
[![Official Docs](https://img.shields.io/badge/docs-nxtkb.com-007c78?style=flat-square)](https://nxtkb.com/zh/docs/setup/ferris-sweep/)
[![Keymap Source](https://img.shields.io/badge/keymap-cradio.keymap-5f6fbf?style=flat-square)](./config/cradio.keymap)
[![ZMK Studio](https://img.shields.io/badge/ZMK-Studio-8b5cf6?style=flat-square)](https://zmk.studio/)

中文 | [English](./README.md)

34 键矮轴分体键盘，支持 USB、蓝牙和 ZMK Studio，采用紧凑的分层键位布局。
这个仓库保存键盘配置、默认键位和固件构建流程；上手与日常使用请从[官方使用指南](https://nxtkb.com/zh/docs/setup/ferris-sweep/)开始。
布局基于 [Sweep](https://github.com/davidphilipbarr/Sweep)。
产品规格、轴体、配件和配色见[官网产品页](https://nxtkb.com/zh/products/ferris-sweep/)。

## 官方文档

- [Ferris Sweep 使用指南](https://nxtkb.com/zh/docs/setup/ferris-sweep/)
- [默认键位与层级](https://nxtkb.com/zh/docs/setup/keymap/ferris-sweep-keymap/)
- [连接设备](https://nxtkb.com/zh/docs/setup/connect/)
- [使用 ZMK Studio 或源码改键](https://nxtkb.com/zh/docs/setup/keymap/how-to-update-keymaps/)
- [固件下载与刷写](https://nxtkb.com/zh/docs/firmware/how-to-flash-a-firmware/)
- [固件配置文件](https://nxtkb.com/zh/docs/firmware/ferris-sweep-configuration/)
- [Codex / ChatGPT 按键使用](https://nxtkb.com/zh/blog/codex-micro-chatgpt-protocol/)

## 固件与改键

[下载发布固件](https://github.com/nxtkb/zmk-config-4-ferris-sweep/releases)，按使用指南选择对应硬件的左右半固件。
日常改键可使用 [ZMK Studio](https://zmk.studio/)；需要修改固件功能时：

1. Fork 本仓库，修改键位或配置文件。
2. 等待 [GitHub Actions](https://github.com/nxtkb/zmk-config-4-ferris-sweep/actions/workflows/build.yml) 构建固件。
3. 下载 UF2，按[刷写指南](https://nxtkb.com/zh/docs/firmware/how-to-flash-a-firmware/)更新对应半边。

本地开发见[自行构建固件](https://nxtkb.com/zh/docs/firmware/build-your-own-firmware/)。

## 仓库结构

| 路径 | 用途 |
| :--- | :--- |
| [`config/cradio.keymap`](./config/cradio.keymap) | 默认层、按键与行为绑定。 |
| [`config/cradio.conf`](./config/cradio.conf) | USB、蓝牙、ZMK Studio 等固件选项。 |
| [`config/west.yml`](./config/west.yml) | 固定的 ZMK 与模块依赖。 |
| [`build.yaml`](./build.yaml) | 左右半及硬件版本的构建目标。 |
| [`.github/workflows/build.yml`](./.github/workflows/build.yml) | GitHub Actions 固件构建入口。 |

## 支持

[产品与购买](https://nxtkb.com/zh/products/ferris-sweep/) · [键鼠测试](https://nxtkb.com/zh/docs/setup/keymap/input-tester/)

Discord：`@lilin0522` · 微信：`nxtkb888`
