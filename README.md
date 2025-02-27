# ZMK Firmware Configuration for Corne Keyboard

This repository contains a custom ZMK firmware configuration for a split ergonomic keyboard, specifically tailored for the [Corne Keyboard](https://github.com/foostan/crkbd) with Nice!Nano v2 controllers and optional Nice!View displays. The configuration includes a versatile keymap with multiple layers (Base, Lower, Raise, and Gaming), custom behaviors, and optimized settings for wireless performance and usability.

## Features

- **Keymap Layers**:
  - **Base**: Standard QWERTY layout with modifiers and layer-switching keys.
  - **Lower**: Symbols, Bluetooth profile switching, and navigation keys.
  - **Raise**: Numbers, additional symbols, and Bluetooth controls.
  - **Gaming**: Optimized layout for gaming with easy access to common keys.

- **Custom Behaviors**:
  - Hold-tap (`kht`) behavior for dual-function keys (e.g., tap for a letter, hold for a modifier or number).
  - Configurable tapping term, quick-tap, and debounce settings for responsive typing.

- **Combos**:
  - `Tab` combo: Press keys at positions 11, 12, and 13 together.
  - `Enter` combo: Press keys at positions 32 and 33 together.

- **Hardware Support**:
  - Built for Nice!Nano v2 boards with Corne left and right shields.
  - Optional Nice!View display support via `nice_view_adapter`.

- **Wireless Optimization**:
  - Configurable Bluetooth TX power for increased range (`CONFIG_BT_CTLR_TX_PWR_PLUS_8`).
  - Bluetooth profile management for up to 5 devices.

## Configuration Files

### `config.west.yml`
Defines the ZMK firmware dependency and project structure:
- Pulls the main ZMK repository from [zmkfirmware/zmk](https://github.com/zmkfirmware/zmk).
- Places custom configuration in the `config` directory.

### `build.yml`
Configures GitHub Actions to build firmware for:
- Nice!Nano v2 with `corne_left` and `corne_right` shields.
- Includes Nice!View display support with the `studio-rpc-usb-uart` snippet.

### Keymap Configuration
The keymap file defines:
- A 5-column matrix transform.
- Four active layers (`default`, `lower`, `raise`, `gaming`) with detailed bindings.
- Custom hold-tap behavior with tap-preferred flavor.
- Combo definitions for `Tab` and `Enter`.

### Settings
Key settings in the configuration include:
- Eager debouncing for responsive keypresses (`CONFIG_ZMK_KSCAN_DEBOUNCE_PRESS_MS=1`, `CONFIG_ZMK_KSCAN_DEBOUNCE_RELEASE_MS=10`).
- Optional deep sleep (`CONFIG_ZMK_SLEEP`) and USB logging (`CONFIG_ZMK_USB_LOGGING`)—uncomment to enable.
- Increased Bluetooth range (`CONFIG_BT_CTLR_TX_PWR_PLUS_8`).

## Getting Started

### Prerequisites
- A Corne keyboard with Nice!Nano v2 controllers.
- [ZMK Firmware](https://zmk.dev/docs) installed and configured.
- [West](https://docs.zephyrproject.org/latest/develop/west/index.html) tool for ZMK dependency management.

## Customization

- Edit the keymap in the configuration file to adjust bindings or add new layers.
- Uncomment optional settings (e.g., `CONFIG_ZMK_USB_LOGGING`) as needed.
- Modify `build.yml` to support additional boards or shields.

## Keymap Layout

### Base Layer
-----------------------------------------------------------------------------------------
|  Q  |  W  |  E  |  R  |  T  |     |  Y  |  U  |  I  |  O  |  P  |
|  A  |  S  |  D  |  F  |  G  |     |  H  |  J  |  K  |  L  |  '  |
|  Z  |  X  |  C  |  V  |  B  |     |  N  |  M  | CTRL| META|  .  |
            | GUI | LWR | SPC |     | ENT | RSE | BSPC|


### Lower Layer
-----------------------------------------------------------------------------------------
|  !  |  @  |  #  |  $  |  %  |     |  ^  |  &  |  *  |  (  |  )  |
| BT1 | BT2 | BT3 | BT4 | BT5 |     | LFT | DWN |  UP | RGT |     |
|BTCLR|     |     |     |     |     |     |     |     |     |     |
            | GUI |     | SPC |     | ENT | ESC | TAB |

### Raise Layer
-----------------------------------------------------------------------------------------
| 1!  |  2@ |  3# |  4$ |  5% |     |  6^ |  7& |  8* |  9( |  0) |
| -_  |  =+ |  {  |  [  |  (  |     |  )  |  ]  |  }  | /?  |  \| |
| `~  |BT S0|BT S1|BT S2|  :  |     |  ;  |  .> | CTRL| META|     |
            | GUI | ESC | SPC |     | ENT |     | TAB |

### Gaming Layer
-----------------------------------------------------------------------------------------
|  1  |  2  |  3  |  4  |  5  |     |  6  |  7  |  8  |  9  |  0  |
| SHFT|  S  |  W  |  F  |  G  |     |  H  |  J  |  K  |  L  |  ;  |
| CTRL|  A  |  S  |  D  | TAB |     |  N  |  M  |  ,  |  .  |  /  |
            | ESC |Base | SPC |     |     |     |Base |

## Contributing

Feel free to submit issues or pull requests for enhancements, bug fixes, or additional layouts. Please ensure any changes are tested on compatible hardware.

## License

This project is licensed under the MIT License, as inherited from the ZMK firmware. See the [ZMK License](https://github.com/zmkfirmware/zmk/blob/main/LICENSE) for details.

## Acknowledgments

- [ZMK Firmware](https://zmk.dev/) for the excellent open-source keyboard firmware.
- The Corne Keyboard community for inspiration and support.
