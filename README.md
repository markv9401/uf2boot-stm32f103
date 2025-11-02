# UF2 bootloader for STM32F103
This project was initially forked off [mmoskal/uf2-stm32f103](https://github.com/mmoskal/uf2-stm32f103), but I had to update some parts of the code to make it build & compatible with QMK UF2BOOT.

Check out the main project for which this was necessary [Cycle 8 Unchained](https://github.com/markv9401/Cycle8_Unchained)

## Flashing bootloader from binaries
You will need a STLink/v2 (or other debugger) to flash it.

## Build instructions
The default target is a generic STM32F103CB board, for example TKD Cycle 8 wired, hot-swappable.
Simply run `build`

## Using the bootloader
### Building for the bootloader
The bootloader occupies the lower 16KiB of flash, so your application must offset its flash contents by 16KiB, starting at 0x80040000. QMK will handle this for you if you use the UF2BOOT bootloader.

### Switching to the bootloader
If QMK is built using UF2BOOT as bootloader, it'll know all the magic bytes to switch to the bootloader when requested.

## Licensing
All contents of the dapboot project are licensed under terms that are compatible with the terms of the GNU Lesser General Public License version 3.
Non-libopencm3 related portions of the dapboot project are licensed under the less restrictive ISC license, except where otherwise specified in the headers of specific files.
The UF2 parts are licensed under MIT.
See the LICENSE file for full details.
