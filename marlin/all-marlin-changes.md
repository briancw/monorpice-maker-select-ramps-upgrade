## Marlin 1.1.9 changes
- 152: filament diameter 1.75
- 313: TEMP_SENSOR_0 set to 11
- 318: TEMP_SENSOR_BED set to 1
- 353: HEATER_0_MAXTEMP 260
- 358: BED_MAXTEMP 100
- 416: Uncomment PIDTEMPBED (turns on PID tuning for bed)
<br><br>
- 531: X_MIN_ENDSTOP_INVERTING true
- 532: Y_MIN_ENDSTOP_INVERTING true
- 533: Z_MIN_ENDSTOP_INVERTING true
<br><br>
- 553-559: Set to "A4988" or "DRV8825"
<br><br>
- (These are for A4988, DRV8829 will use different settings)
- 611-650:
  - #define DEFAULT_AXIS_STEPS_PER_UNIT   { 80, 80, 400, 96 }
  - #define DEFAULT_MAX_FEEDRATE          { 200, 200, 8, 25 }
  - #define DEFAULT_MAX_ACCELERATION      { 800, 700, 100, 1000 }
  - #define DEFAULT_ACCELERATION          800
  - #define DEFAULT_RETRACT_ACCELERATION  800
  - #define DEFAULT_TRAVEL_ACCELERATION   1000
  - #define DEFAULT_XJERK                 10.0
  - #define DEFAULT_YJERK                 10.0
  - #define DEFAULT_ZJERK                  0.4
  - #define DEFAULT_EJERK                  2.0
<br><br>
- 851: INVERY_X_DIR true
- 852: INVERT_Y_DIR false
<br><br>
- 891: Z_MAX_POS 180

### PID Settings
##### Hotend
- // Monoprice Maker Select V2 (Tested by Brian)
- #define DEFAULT_Kp 22.44
- #define DEFAULT_Ki 1.61
- #define DEFAULT_Kd 78.14

##### Bed
- // Monoprice Maker Select V2 (Tested by Brian)
- #define DEFAULT_bedKp 285.15
- #define DEFAULT_bedKi 55.25
- #define DEFAULT_bedKd 367.92