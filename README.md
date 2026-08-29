# NXTKB Ferris Sweep ZMK Config

[![Firmware Build](https://img.shields.io/github/actions/workflow/status/nxtkb/zmk-config-4-ferris-sweep/build.yml?branch=main&label=firmware%20build&style=flat-square)](https://github.com/nxtkb/zmk-config-4-ferris-sweep/actions/workflows/build.yml)
[![Docs Status](https://img.shields.io/website?url=https%3A%2F%2Fnxtkb.com%2Fdocs%2Fsetup%2Fkeymap%2Fferris-sweep-keymap%2F&label=docs&up_message=online&up_color=2f6f6f&down_message=offline&down_color=8b1e3f&style=flat-square)](https://nxtkb.com/docs/setup/keymap/ferris-sweep-keymap/)
[![Keymap Source](https://img.shields.io/badge/keymap-cradio.keymap-5f6fbf?style=flat-square)](./config/cradio.keymap)
[![ZMK Config](https://img.shields.io/badge/ZMK-cradio.conf-6b7280?style=flat-square)](./config/cradio.conf)
[![ZMK Studio](https://img.shields.io/badge/ZMK-Studio-8b5cf6?style=flat-square)](https://zmk.studio/)
[![Input Tester](https://img.shields.io/website?url=https%3A%2F%2Finput-test.nxtkb.com%2F&label=input%20tester&up_message=online&up_color=2f6f6f&down_message=offline&down_color=8b1e3f&style=flat-square)](https://input-test.nxtkb.com/)

[中文](./README-zh_CN.md) | English

This repository contains the ZMK firmware configuration for the NXTKB Ferris
Sweep keyboard. It is based on the [Sweep](https://github.com/davidphilipbarr/Sweep)
layout, builds with [ZMK](https://github.com/zmkfirmware/zmk), and supports
[ZMK Studio](https://zmk.studio/) for live keymap edits when the firmware
enables it. Use this repository to inspect, fork, and build firmware. For
setup, flashing, keymap diagrams, and day-to-day usage notes, start with the
public NXTKB docs.

## Official Docs

- [Getting Started](https://nxtkb.com/docs/setup/)
- [Ferris Sweep Keymap](https://nxtkb.com/docs/setup/keymap/ferris-sweep-keymap/)
- [Ferris Sweep Configuration](https://nxtkb.com/docs/firmware/ferris-sweep-configuration/)
- [How to Update Keymaps](https://nxtkb.com/docs/setup/keymap/how-to-update-keymaps/)
- [How to Flash Firmware](https://nxtkb.com/docs/firmware/how-to-flash-a-firmware/)
- [Keyboard & Mouse Test](https://nxtkb.com/docs/setup/keymap/input-tester/)
- [Using Codex Micro on Ferris Sweep](https://nxtkb.com/blog/codex-micro-chatgpt-protocol/)

Chinese docs are also available:

- [入门指南](https://nxtkb.com/zh/docs/setup/)
- [Ferris Sweep 键位映射](https://nxtkb.com/zh/docs/setup/keymap/ferris-sweep-keymap/)
- [Ferris Sweep 配置文件](https://nxtkb.com/zh/docs/firmware/ferris-sweep-configuration/)

## Repository Layout

- `config/cradio.keymap`: layers, key bindings, home-row modifiers,
  conditional layers, mouse layer, bootloader keys, soft-off behavior, and ZMK
  Studio unlock.
- `config/cradio.conf`: board-level ZMK settings for this keyboard.
- `build.yaml`: GitHub Actions build matrix for generated firmware artifacts.
- `.github/workflows/build.yml`: firmware build workflow that reuses ZMK's
  user config build.

## Pinned Dependencies

[![ZMK revision](https://img.shields.io/badge/zmk-b66b8b4e-5f6fbf?style=flat-square)](https://github.com/nxtkb/zmk/tree/b66b8b4e07655d16c01d14bfa06e2f7f6c46025f)
[![zmk-behavior-report revision](https://img.shields.io/badge/zmk--behavior--report-476f43da-2f6f6f?style=flat-square)](https://github.com/nxtkb/zmk-behavior-report/tree/476f43da1f98b4a6150c9c0e499a257bd64a29a0)

The firmware build is pinned through `config/west.yml`:

| Project | Remote | Revision |
| :--- | :--- | :--- |
| `zmk` | `nxtkb/zmk` | `b66b8b4e07655d16c01d14bfa06e2f7f6c46025f` |
| `zmk-behavior-report` | `nxtkb/zmk-behavior-report` | `476f43da1f98b4a6150c9c0e499a257bd64a29a0` |

## Firmware and Keymap Workflow

For persistent configuration changes:

1. Fork this repository.
2. Edit `config/cradio.keymap` or `config/cradio.conf`.
3. Let GitHub Actions build the firmware artifacts.
4. Flash the generated UF2 file to the matching keyboard half.

For quick keymap edits, use [ZMK Studio](https://zmk.studio/) when this
firmware supports it. For the full decision guide, see
[How to Update Keymaps](https://nxtkb.com/docs/setup/keymap/how-to-update-keymaps/).

### Codex Micro build

The keymap includes a conditional Codex layer for the left half. The public
`zmk-feature-codex-micro` module is pinned in `config/west.yml`. The default
GitHub Actions workflow builds the left firmware with USB and Bluetooth Codex
transports and builds the right half as a normal split peripheral.

The pinned `nxtkb/zmk` revision contains the USB HID interrupt-OUT support
required by the module, so no separate patch step is needed. The right half
continues to use the normal firmware. Release builds enable the module's minimal
compatibility identity, which changes only USB VID/PID and Bluetooth PnP VID/PID;
user-visible keyboard names remain configurable. These identifiers do not imply
OpenAI certification, and the undocumented discovery behavior may change in
future ChatGPT releases.

## Keymap Summary

The complete diagrams and layer-by-layer explanations live on the website:

- [Ferris Sweep Keymap](https://nxtkb.com/docs/setup/keymap/ferris-sweep-keymap/)
- [Ferris Sweep 键位映射](https://nxtkb.com/zh/docs/setup/keymap/ferris-sweep-keymap/)
- [View the latest keymap in keymap-drawer](https://keymap-drawer.streamlit.app/?zmk_url=https%3A%2F%2Fgithub.com%2Fnxtkb%2Fzmk-config-4-ferris-sweep%2Fblob%2Fmain%2Fconfig%2Fcradio.keymap)

Current default layers:

- Default layer: character input with home-row modifiers.
- Numbers and navigation layer: hold the right `TAB` layer key.
- Symbols layer: hold the left `TAB` layer key.
- Function layer: hold both `TAB` layer keys for Bluetooth profiles, output
  switching, Codex layer entry, ZMK Studio unlock, and soft off.
- Mouse layer: enter from the symbols layer with `SPACE`, then leave with `P`
  or `Q`.
- Codex layer: enter with `I` on the function layer; use `Q`–`Y` for Agents
  1–6, `A`/`S`/`D`/`F` for Approve/Split/Decline/Fast, `H`/`J` for
  Voice/Send, and `P` to exit.

## Bootloader and Flashing Notes

To enter bootloader mode, use one of these methods:

1. Press the keymap's `Boot` key while the keyboard is connected.
2. Double-click the reset button.
3. Short `RST` to `GND` twice if the reset button is not available.

Firmware artifact names normally indicate the target half:

- `left`: left half firmware.
- `right`: right half firmware.
- `reset`: reset firmware for clearing Bluetooth pairing information.

If you only changed key bindings or the keyboard name, you usually only need to
flash the left half. If you changed split behavior, board settings, or
right-half behavior, flash the affected half as well. See
[How to Flash Firmware](https://nxtkb.com/docs/firmware/how-to-flash-a-firmware/)
before updating a board.
