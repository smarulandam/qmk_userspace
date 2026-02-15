# ⌨️ TiagoCode QMK Userspace

![QMK Userspace](https://img.shields.io/badge/QMK-userspace-1f883d?style=for-the-badge)
![Split Ergo](https://img.shields.io/badge/Split-Ergonomic-0a66c2?style=for-the-badge)
![Layers](https://img.shields.io/badge/Layers-6-orange?style=for-the-badge)

One layout philosophy, multiple split keyboards.

This repository is my external QMK userspace with consistent, coding-focused keymaps across different split ergonomic boards.

## Highlights

- Shared 6-layer system across keyboards.
- Home-row friendly modifiers and tap-hold keys.
- Fast nav/symbol/num workflows for coding.
- Per-board extras (OLED, encoders, RGB tuning).
- Build locally or via GitHub Actions.

## Supported Keymaps

| Keyboard | Target | In `qmk.json` |
| --- | --- | --- |
| SplitKB Kyria rev3 | `splitkb/kyria/rev3:tiagocode` | Yes |
| SplitKB Kyria | `splitkb/kyria:tiagocode` | Yes |
| Corne rev1 | `crkbd/rev1:tiagocode` | Yes |
| Dasky Reverb | `dasky/reverb:tiagocode` | Yes |
| SplitKB Aurora Sofle v2 | `splitkb/aurora/sofle_v2:tiagocode` | Yes |
| SplitKB Aurora Lily58 | `splitkb/aurora/lily58:tiagocode` | Yes |
| OMKBD ErgoDash | `omkbd/ergodash:tiagocode` | No (keymap exists, optional target) |

## Layer Stack

| Layer | Purpose |
| --- | --- |
| `QWERTY` | Base typing layer |
| `NAVIGATION` | Arrows, home/end, modifiers, quick nav |
| `NUMPAD` | Numpad and operators |
| `SYMBOLS` | Programming symbols and punctuation |
| `FUNCTIONS` | F-keys and utility access |
| `ADJUST` | RGB/lighting controls |

Common tap-hold aliases used across boards:

- `NUM_TAB = LT(_NUMPAD, KC_TAB)`
- `QUO_FUN = LT(_FUNCTIONS, KC_QUOT)`
- `LCAPS` / `RCAPS` as shift-tap modifiers

## Quick Start

1. Install and initialize QMK CLI (once):
```bash
qmk setup
```
2. Clone this repo and enter it:
```bash
git clone <your-fork-url>
cd qmk_userspace
```
3. Point QMK to this userspace:
```bash
qmk config user.overlay_dir="$(pwd)"
```
4. Ensure `qmk_firmware` home is configured:
```bash
qmk config user.qmk_home=/path/to/qmk_firmware
```

## Build

Compile one target:

```bash
qmk compile -kb splitkb/kyria/rev3 -km tiagocode
```

or:

```bash
make splitkb/kyria/rev3:tiagocode
```

Compile all targets from `qmk.json`:

```bash
qmk userspace-compile
```

## Flash

For boards supported by QMK flashing:

```bash
qmk flash -kb splitkb/kyria/rev3 -km tiagocode
```

For UF2-based boards, compile and copy the generated `.uf2` to the boot drive.

## License

GPL-2.0-or-later. See `LICENSE`.
