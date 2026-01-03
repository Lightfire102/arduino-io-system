# System Architecture

This project started off as a simple Arduino I/O experiment 

At a high level: 
- The Arduino handles all input (buttons) and output (LEDs, buzzer)
- The main loop continuously takes in inputs and updates the corresponding outputs
- Serial output is used as a lightweight debugging tool

File responsibilities (current state):
- `blink_reference.ino` - Initial code for the simple LED experiment
- `arduino_sketch.ino` - Complete code for the simon game as well with serial debugging included

