https://www.youtube.com/watch?v=-xndPRoVk5g

long pins are the positive (anode), short ones negative (cathode)
current coming out of ardu: 5v (positive), ground (GND, negative)
use bright (red) cables for positive, darker (blue, brown) for negative

**calculate resistor value for LED**
R = V / I 
![[Screen Shot 2022-06-28 at 17.10.33.png]]

total voltage = 5
minus what LED needs = 5 - 2 = 3
3 / 0.01 (the current of LED) = 300 om resistance needed
===do not go below 300 to avoid damaging the LED ===

**breadboard**
numbers rows are wired so they are the same wire, they vary according to the vertical letter columns

**serial monitor on the IDE**
Serial.begin(2600)
match the baud rate to the config on the UI
Serial.print("a")