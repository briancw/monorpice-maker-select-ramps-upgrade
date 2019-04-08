# Install a ramps board
### Label All wires
You're going to need to cut the ends off of some wires, so label everything first.
Many wires are indistinguishable, so if you forget what it is you'll have a miserable time tracing it.

### Install stepper motor drivers into ramps board
- Install heatsinks onto the steppers
- Determine orientation by lining up labels on the drivers and on the ramps board.
Don't trust the location of the potentiometer or other reference pics. Getting this wrong will likely destroy parts.

### Tune the steppers
- https://www.youtube.com/watch?v=9moNexk8Kg4
##### A4988
- (For A4988, get the amps of the motor, multiply by 8, multiple by resister in Ohms (0.1), reduce by 10% for safety)
- E/X/Y should be tuned to 0.684V
- Z should be tuned to 0.864V
##### DRV8825
- (For DRV8825, get the amps of the motor, divide by 2, reduce by 10% for safety)
- E/X/Y should be tuned to 0.4275
- Z should be tuned to 0.54

### Install the Ramps board onto the Arduino

### Connect all the wires
- Power in and hot bet go in the large screw terminals.
- Hot end and Fan go in the smaller screw terminals
- Motor wires go in the labeled blocks near the motor drivers
- Endstops go in the section labeled "X-, Y-, Z-" Connect between the row S and -
- Hot end temperature sensor goes on T0
- Bed temperature sensor goes on T1

# Install firmware

### Klipper or Marlin
- Refer to the klipper.md or marlin.md file from here
- Saved working good configurations are in the folders klipper and marlin

### Test that motors have been wired correctly
- POWER OFF THE RAMPS BOARD BEFORE DISCONNECTING OR CONNECTING MOTORS
- Using Octoprint or Printrun, test moving the motors and checking the endstops.
- If a motor is moving in the wrong direction just flip the pins in the opposite orientation

