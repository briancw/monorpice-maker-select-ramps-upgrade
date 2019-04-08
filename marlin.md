# How to install Marlin v1.1.9

### Flash the firmware
- Download the Arduino IDE from arduino.cc
- Download the marlin firmware from https://github.com/MarlinFirmware/Marlin
- My entire configuration.h for marlin version 1.1.9 is also provided here (I have A4988 motor drivers)
- Alternatively, you can just change the relevant lines from the configuration.md file here

### Tune Extruder and Hotend PID settings
- Use Octoprint's terminal to run the command "M303 S200 C10"
- After the print head heats and cools 10 times, it will return values which you can place in the Configuration.h file
- Use the command "M303 E-1 S70 C10" to get PID values for the bed
- I'm using temperatures of 200 and 70 for hotend and bed temps respectively. If you prefer different values, change accordingly.