# dumbpad

[Original](https://github.com/imchipwood/dumbpad/tree/master/hotswap_rgb)

4x4 keys macropad with RGB lightning designed by [imchipwood](https://github.com/imchipwood) and [deveth0](https://www.github.com/deveth0).

This version of dumpad uses R2040 controller on Arduino Pro Micro compatible board driven by [Vial](https://get.vial.today/) firmware.

## Installation

### Prerequisites

Install Vial Build Environment following [official guide](https://get.vial.today/docs/porting-to-vial.html#1-prepare-your-build-environment). Verify your installation by building example keyboard configuration:

```shell
~/vial-qmk $ make vial_example/vial_rp2040:vial:build
```

### Build

Copy `v3x_rp2040` folder to `keyboards/vial/` directory in your Vial installation. This is a patched `v3x` configuration with RP2040 support.

Build the firmware using `make` command with certain target:

```shell
~/vial-qmk $ make dumbpad/v3x_rp2040:vial:build
```

Result firmware binary will be created in Vial installation directory.

### Flash

There are 2 ways to update the firmware on RP2040:

1. Upload file manually
    1. Connect board to the computer
    2. Reset to bootloader pressing BOOT and RESET button simultaneously.
    3. Copy the `dumbpad_v3x_rp2040_vial.uf2` file from the Vial Build Environment folder to the connected USB Mass Storage device.
2. Using Vial tools
    1. Run `make vial_example/vial_rp2040:vial:flash` command
    2. Reset to bootloader
    3. Wait for flashing to complete.
