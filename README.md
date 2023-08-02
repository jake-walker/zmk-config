# ZMK Configs

This repo contains ZMK configs for some custom keyboards.

The ZMK ARDUX keymap (ardux.dtsi) used in configs is part of the [arduxio/zmk-ardux](https://github.com/arduxio/zmk-ardux/) project.

## Build Instructions

Use the VS Code Dev Container for running the below instructions.

```bash
apt update
apt install build-essential -y
git clone https://github.com/zmkfirmware/zmk.git
west init -l config
west update
west zephyr-export
pip3 install --user -r zephyr/scripts/requirements.txt

west build -s zmk/app -b seeeduino_xiao_ble -- -DSHIELD=bruh8 -DZMK_CONFIG=${PWD}/config
```

Flash the generated `build/zephyr/zmk.uf2`.
