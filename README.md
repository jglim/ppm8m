# PPM8M

PPM8M is a fork of [davidbuzz/BuzzsArduinoCode](https://github.com/davidbuzz/BuzzsArduinoCode) that converts up to 8 channels of RC PWM signals into a single PPM signal, and runs on an **8 MHz** Arduino Pro Mini (atmega328p) board.

---
_Original-ish readme:_

## How
* Use Arduino IDE to program this firmware onto the Arduino chip.
* Connect up to 8 RC PWM input signals so that the wires go to:
     Red = `5V`
     Black = `GND`
     White = PWM pins `D0, D1, D2, D3, D4, D5, D6, D7`

* Connect the PPM output so that the wires go to:
     Red = `5V`
     Black = `GND`
     PPM out = `D10` 

## Tips:  
* Any channel without a connected PWM input will emit a default value (1500 for all channels except throttle, which is 1100).
* Disconnecting any channel after booting will cause the system to use the last-known position of the input, until a good signal returns.
* D0 and D1 are also used by the Serial Programmer/bootloader. You can not reprogram this unit with PWM inputs still connected to D0 and D1, Unplug unit from PWM sources before re-programming.
* This is not a "failsafe" unit, it has no failsafe functionality.