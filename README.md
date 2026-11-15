# NXTKB Ferris Sweep ZMK Config

[![Firmware Build](https://img.shields.io/github/actions/workflow/status/nxtkb/zmk-config-4-ferris-sweep/build.yml?branch=main&label=firmware%20build&style=flat-square)](https://github.com/nxtkb/zmk-config-4-ferris-sweep/actions/workflows/build.yml)
[![Official Docs](https://img.shields.io/badge/docs-nxtkb.com-007c78?style=flat-square)](https://nxtkb.com/docs/setup/ferris-sweep/)
[![Keymap Source](https://img.shields.io/badge/keymap-cradio.keymap-5f6fbf?style=flat-square)](./config/cradio.keymap)
[![ZMK Studio](https://img.shields.io/badge/ZMK-Studio-8b5cf6?style=flat-square)](https://zmk.studio/)

[中文](./README-zh_CN.md) | English

A compact 34-key low-profile split keyboard with a layered keymap, USB, Bluetooth, and ZMK Studio support.
This repository contains the keyboard configuration, default keymap, and firmware build workflow.
Start with the [official user guide](https://nxtkb.com/docs/setup/ferris-sweep/) for setup and everyday use.
The layout is based on [Sweep](https://github.com/davidphilipbarr/Sweep).
See the [product page](https://nxtkb.com/products/ferris-sweep/) for specifications, switches, accessories, and colors.

## Official Docs

- [Ferris Sweep User Guide](https://nxtkb.com/docs/setup/ferris-sweep/)
- [Default Keymap and Layers](https://nxtkb.com/docs/setup/keymap/ferris-sweep-keymap/)
- [Connect to Your Device](https://nxtkb.com/docs/setup/connect/)
- [Edit Keymaps with ZMK Studio or Source](https://nxtkb.com/docs/setup/keymap/how-to-update-keymaps/)
- [Download and Flash Firmware](https://nxtkb.com/docs/firmware/how-to-flash-a-firmware/)
- [Firmware Configuration Files](https://nxtkb.com/docs/firmware/ferris-sweep-configuration/)
- [Codex / ChatGPT Controls](https://nxtkb.com/blog/codex-micro-chatgpt-protocol/)

## Firmware and Keymap Changes

[Download release firmware](https://github.com/nxtkb/zmk-config-4-ferris-sweep/releases) and choose the matching left/right pair in the user guide.
Use [ZMK Studio](https://zmk.studio/) for everyday keymap edits. To change firmware features:

1. Fork this repository and edit the keymap or configuration files.
2. Let [GitHub Actions](https://github.com/nxtkb/zmk-config-4-ferris-sweep/actions/workflows/build.yml) build the firmware.
3. Download the UF2 files and [flash the matching halves](https://nxtkb.com/docs/firmware/how-to-flash-a-firmware/).

For local development, see [Build Your Own Firmware](https://nxtkb.com/docs/firmware/build-your-own-firmware/).

## Repository Layout

| Path | Purpose |
| :--- | :--- |
| [`config/cradio.keymap`](./config/cradio.keymap) | Default layers, keys, and behavior bindings. |
| [`config/cradio.conf`](./config/cradio.conf) | USB, Bluetooth, ZMK Studio, and other firmware options. |
| [`config/west.yml`](./config/west.yml) | Pinned ZMK and module dependencies. |
| [`build.yaml`](./build.yaml) | Build targets for each half and hardware variant. |
| [`.github/workflows/build.yml`](./.github/workflows/build.yml) | GitHub Actions firmware build entry point. |

## Support

[Product and purchase](https://nxtkb.com/products/ferris-sweep/) · [Keyboard & Mouse Test](https://nxtkb.com/docs/setup/keymap/input-tester/)

Discord: `@lilin0522` · WeChat: `nxtkb888`
