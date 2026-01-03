# Issue: Incorrect LED Mapping

## Symptom
When a button was pressed, the **wrong LED illuminated**.  
For example, pressing one color button would trigger a different color LED than expected.

## Diagnosis
Initial inspection showed that the hardware wiring was correct, but the observed behavior did not match the intended input-to-output relationship.

Reviewing the firmware revealed that some LED pin assignments in the code did not correspond to the actual physical wiring on the breadboard.

## Root Cause
The issue was caused by an **incorrect pin mapping in the firmware**, where LED constants were assigned to the wrong GPIO pins.

This resulted in valid input signals driving unintended outputs.

## Fix
The pin definitions in the code were updated to correctly match the physical LED wiring.

No hardware changes were required — the fix was purely software-based.

## Result
After correcting the pin mappings:
- Each button correctly illuminated its corresponding LED
- Serial debug output aligned with physical behavior
- System behavior matched the intended design

## Lessons Learned
- Firmware pin definitions must always reflect the physical wiring
- Logical errors can mimic hardware faults
- Verifying pin mappings early prevents misleading debugging paths
