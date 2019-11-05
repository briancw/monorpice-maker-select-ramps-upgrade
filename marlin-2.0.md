# Install and configure Marlin 2.0
- 1. Install the VSCODE extension PlatformIO. This will be used to build the firmware.
- 2. Git clone the Marlin 2.0 branch. (https://github.com/MarlinFirmware/Marlin/tree/bugfix-2.0.x)[https://github.com/MarlinFirmware/Marlin/tree/bugfix-2.0.x]
- 3. In VSCode, using PlatformIO, open a project and select the marlin 2.0 folder (whever the platformio.ini file is located)
- 4. In platformio.ini, modify the setting, "default_envs" to "default_envs = LPC1768"
- 5. Copy the Configuration.h and Configuration_adv.h config from this repo's marlin-2.0 folder to the 'marlin' folder in VSCode
- These configs are based on templates supplied for Wanhao Duplicator I3 printers for Marlin 2.0
- I made heavy modifications, so optimally, you should review each file.

6. Use the command pallet to run PlatformIO: Build
7. After building, if there were no errors, you'll have a "firmware.bin" file in .pio/build/LPC1768/
8. Copy this file to the Microsd card for the SKRv1.3 board either via USB or by pluggin the card into your computer.
9. Restart the SKR v1.3 and the firmware will be flashed.