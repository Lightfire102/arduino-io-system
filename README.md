## arduino-io-system
This project shows the evolution of a basic Arduino GPIO output (blinking a single LED) into a fully functional input/output system using multiple LEDs and buttons, ending with a partial Simon memory game. The point of this was for learning system growth, modular firmware structures and debugging using serial output. 
# Arduino I/O System (Blink → Simon Game) with Serial Debugging

## Hardware Used
- Arduino (UNO or similar)
- LEDs (x4)
- Push buttons (x4)
- Resistors (LED current limiting + optional pull-ups/pull-downs)
- Breadboard + jumper wires
- USB serial (Serial Monitor)

## System Architecture
- Inputs: push buttons (digital reads)
- Outputs: LEDs (digital writes)
- Logic: state machine controlling sequence playback + input checking
- Debug: serial prints for state transitions, button reads, and error diagnosis

See: `docs/architecture.md`

## Repo Structure
- `hardware/`  : build photos + schematic
- `firmware/`  : source code (modular)
- `debug/`     : serial logs, issues fixed, evidence
- `docs/`      : system evolution + testing checklist

## System Evolution
### Phase 1: GPIO Output Bring-Up (Blink)
- Verified basic output control with a single LED
- Evidence: `hardware/phase1_blink/`

### Phase 2: Input + Output Expansion (Simon Build)
- Added multiple LEDs + buttons
- Implemented state-based logic
- Evidence: `hardware/phase2_simon_build/`

### Phase 3: Debugging + Validation (Serial)
- Used serial prints to debug state transitions and button detection
- Evidence: `debug/serial/serial_monitor_output.png`
- Fixed issues documented in: `debug/issues_fixed/`

See: `docs/system_evolution.md`

## Firmware Overview
Key modules:
- `io.cpp/.h`     : pin mappings and basic I/O functions
- `simon.cpp/.h`  : game logic + state machine
- `debug.cpp/.h`  : debug print helpers and instrumentation

## Debugging & Testing (Highlights)
### Issue 1: Button press detected twice
- Symptom: single press triggered two inputs
- Diagnosis: serial timestamps + state logs
- Fix: software debounce / timing filter
- Evidence: `debug/issues_fixed/issue1_double_press.md`

### Issue 2: Incorrect LED mapping
- Symptom: wrong LED illuminated for given input in Arduino IDE
- Fix: corrected pin map abstraction
- Evidence: `debug/issues_fixed/issue2_wrong_led_mapping.md`

## Results
- Pressing certain buttons will cause the respective LED to light up and a unique buzzer sound to be played. 

## Lessons Learned
- I mistakenly placed the buttons in the board incorrectly because I was not aware of what the proper way of inserting the button into the breadboard. However, using my multimeter, i was able to check the button by selecting the wifi looking setting on the multimeter and press down on the button while holding the probes to see the correct placement of the buttons. Idk how else to explain that but I have a picture and video of me doing so!

## Future Improvements
- After completing this project, one thing I would change are the type of wires I used. I was annoyed by the messiness of the wiring and how long they were. So if I was to redo this project, I would change the type of wires I would use and use a wire cutter for more exact wiring length for a cleaner setup. 


https://github.com/user-attachments/assets/77d217d4-e4e7-4c52-8d5b-dc160ce37fb6

