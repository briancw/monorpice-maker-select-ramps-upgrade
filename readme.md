# Install a new board

## 1. Label All wires
You're going to need to cut the ends off of some wires, so label everything first.

## 2. Configure jumper pins
#### SKR v1.3
- In the center of the board is a power selector which lets you power the board via USB or external power.
- You can set this to the right when programming the board or testing with a pc. Keep it to the left when running with 12v power or you'll kill anything plugged into the USB port.
- Under each stepper driver are microstepping control pins. Remove all of them where using a TMC2209. Keep all in if using an A4988.
- Near the stepper motors are 4 red jumper positions for enabling UART mode. Use a jumper for any steppers controller with a TMC2209.
- Remove anything else on the board.
#### Ramps
- Near the top of the board is a power selector which lets you power the board via USB or external power. Keep this to the right two pins.
- Under each stepper driver are pins to control microstepping. Keep all 4 pins installed and to the right.

## 3. Install stepper motor drivers
#### SKR v1.3
- For TMC2209 drivers, everything is color coded and only fits one way.
- For A4988/DRV8825 drivers, match pin labels and board labels carefully.
#### Ramps
- Determine orientation by lining up labels on the drivers and on the ramps board.
- Don't trust the location of the potentiometer or other reference pics. Getting this wrong will likely destroy parts.

### Install stepper motor drivers into ramps board
- Determine orientation by lining up labels on the drivers and on the ramps board.
- Don't trust the location of the potentiometer or other reference pics. Getting this wrong will likely destroy parts.

## 4. Tune the steppers
#### TMC2209
- Tuning is done in software
- We'll use the same values as the DRV8825 drivers (0.4275v and 0.864v) in software.
- https://www.youtube.com/watch?v=9moNexk8Kg4
#### A4988
- (For A4988, get the amps of the motor, multiply by 8, multiple by resister in Ohms (0.1), reduce by 10% for safety)
- E/X/Y should be tuned to 0.684V
- Z should be tuned to 0.864V
#### DRV8825
- (For DRV8825, get the amps of the motor, divide by 2, reduce by 10% for safety)
- E/X/Y should be tuned to 0.4275
- Z should be tuned to 0.54

## 5. If using a Ramps 1.4, install the ramps board onto an Arduino 2560 Mega


## 5. Wiring
- Power in, Bed Heater, Hot End Heater, and Part fan use screw terminals
- Motor wires go in the labeled blocks

#### SKR v1.3
- Endstops go in the X-, Y-, and Z- plugs. Connect on the bottom two plugs. "G" and "S". (This pulls the signal to ground when tripped)
- Hot end temperature sensor goes on TH0
- Bed temperature sensor goes on TB

#### Ramps 1.4
- Endstops go in the X-, Y-, and Z- plugs. Connect between the row "S" and "-". (This pulls the Signal to ground when tripped)
- Hot end temperature sensor goes on T0
- Bed temperature sensor goes on T1

## 6. Install firmware
- For SKR v1.3 and TMC2209 drivers, see [marlin-2.0.md](marlin-2.0.md)
- For Ramps 1.4 and DRV2285/A4988 drivers, see [klipper.md](klipper.md)
- Or, for Ramps 1.4 and DRV2285/A4988 drivers, see [marlin.md](marlin.md)

### Klipper or Marlin
- Refer to the klipper.md or marlin.md file from here
- Saved working good configurations are in the folders klipper and marlin

## 7. Test that motors have been wired correctly
- POWER OFF THE RAMPS BOARD BEFORE DISCONNECTING OR CONNECTING MOTORS
- Using Octoprint or Printrun, test moving the motors.
- If a motor move oposite to how you expected, either flip the wires around or change the motor direction in firmware.
- Check that the endstops are working by moving the motor and triggering them with your finger.

## 8. Adjust Z offset
- You may have a different Z offset than one of the configs here depending on your carriage.
- You can compensate for this via the bed leveling screws, by moving the Z endstop, or in firmware configuration.
