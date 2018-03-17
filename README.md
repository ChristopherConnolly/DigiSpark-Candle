# DigiSpark-Candle
A candle effect created using an ATTiny85 based Chinese DigiSpark Clone, an LDR, and a PL9832 LED

The PL9832 is an addressable RGB LED, and is connected to Pin 0. 

The LDR is connected directly from ground to Pin 3. Despite what I have read, I found that there is no need to use an external resistor with the LDR, as Pin 3 is connected to a perfectly fine pullup resistor.

This code works to turn off the LED and sleep the controller in bright daylight using my particular LDR. Of course with different components you may need to adjust the level.

Similarly you will probably want to alter the switch statement. I attempted to make a procedural flicker effect, but I was not happy with the result.

There is a test routine enclosed in the code. This simply flashes the LED for whatever the analogue input is - ie. 30 times for a value of 30, etc. This sounds silly, but I found it worked really well, and was quite easy to use.

Sleep mode is implemented, using code from https://gist.github.com/dwhacks/8055287#file-attiny85_watchdog_example-ino. Without sleep mode power consumption was approximately 30ma in use and 15ma in standby. With sleep mode power consumption is approximately 15-20ma in use, and 7ma in standby.

The major power consumer on this board is the voltage regulator, which draws approximately 5ma at all times. An improvement on this design would be to use a bare ATTiny85 and dispense with the board, however the board provides a very convenient platform.

I have one of these wired up to an old 4.2v lithium ion laptop battery, and it provides at least 1 weeks runtime outdoors when used as an ornament.
