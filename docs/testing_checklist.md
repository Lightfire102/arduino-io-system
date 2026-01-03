# Testing Checklist

This checklist is how I verified the system worked as expected.

## Power & Setup
- [x] Board powers on correctly
- [x] `setup()` runs and prints confirmation over serial

## Inputs
- [x] Each button press is detected
- [x] Button wiring verified with multimeter continuity test
- [x] No false triggers when buttons are not pressed

## Outputs
- [x] Correct LED turns on for each button
- [x] Buzzer plays correct tone per color
- [x] LEDs turn off when buttons are released

## Debugging
- [x] Serial output confirms button presses
- [x] Reset behavior observed and verified
- [x] Fixed incorrect LED mapping bug

This helped me avoid guessing and actually confirm what the system was doing.

