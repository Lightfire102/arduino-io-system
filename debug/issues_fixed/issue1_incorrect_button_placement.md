# Issue: Button Misplacement on Breadboard

## Problem
The push buttons were initially inserted incorrectly into the breadboard due to a misunderstanding of the internal pin connections of a standard tactile switch. As a result, button presses were not being detected reliably by the microcontroller.

## Diagnosis
To investigate the issue, a multimeter was used in **continuity mode** (audible mode, often represented by a “sound wave” or Wi-Fi–like symbol).

By placing probes across different pairs of button pins and pressing the button, I was able to identify which pins were internally connected when the button was actuated.

## Root Cause
The button was rotated **90 degrees from the correct orientation**, causing both legs on one side of the switch to be placed on the same breadboard node. This prevented a proper logic-level change from occurring when the button was pressed.

## Fix
The button was removed and reinserted so that the two internally connected pin pairs straddled the breadboard’s center gap.

Continuity was rechecked using the multimeter to confirm correct pin behavior before reconnecting the circuit.

## Result
After correcting the button orientation:
- Button presses were detected consistently
- LEDs responded correctly
- Buzzer tones played as expected
- Serial debug output displayed correct button press messages

## Lessons Learned
- Tactile switches have internal pin pairings that must be understood before insertion
- Continuity testing is an effective way to validate hardware before debugging firmware
- Hardware verification should be an early step when diagnosing input-related issues
