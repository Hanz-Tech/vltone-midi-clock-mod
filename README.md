
# Casio VL-1 VL-Tone MIDI Clock Mod

This mod enabled pattern saved in the Vl-1 to be synced to MIDI clock.

VL-1 Has two "one key play button" to play notes stored in a pattern.

We can use this to simulate button press via pulse signal

## Hardware Mod needed on the VL1

We need to solder 3 wires to the MCU pin

Counting from left to right we need to solder wires to following pins on the upper row of the micro-controller : 

```
Pin #5 -> This is a common line

Pin #11 -> One Key play 1

Pin #13 -> One Key play 2
```

![IMG_8899 1](https://github.com/user-attachments/assets/b04ca98a-dfae-496e-b6c8-8c767480ac9b)

We need two of these transistors. One for each "one key play" button. Both emisor are soldered to the "common line" on pin 5 and the collector is attached to pin 11 and 13 respectively. The base is soldered to the tip and ring of the TRS jack with a 270kOhms resistor in between. One TRS mini jack is enough for both circuit.

![pics/2N2222-NPN-1869953919.png](https://github.com/Hanz-Tech/vltone-midi-clock-mod/blob/main/pics/2N2222-NPN-1869953919.png)

### Reference diagram

We're essentially doing something similar to this diagram except instead of connection to the switch points, we're soldering to the pins on the micro-controller directly.

![](https://github.com/Hanz-Tech/vltone-midi-clock-mod/blob/main/pics/vltone.png)

## MIDI Clock to Trigger Converter

Hardware needed

* https://www.adafruit.com/product/4884
* https://www.adafruit.com/product/4740
* A potentiometer to select speed
* LED
* 3D printed box (files are in cad folders)
* 3.5mm TRS jack

![](https://github.com/Hanz-Tech/vltone-midi-clock-mod/blob/main/pics/box_closed.png)
![](https://github.com/Hanz-Tech/vltone-midi-clock-mod/blob/main/pics/box_open.png)

### Code

This code essentially converts MIDI clock to trigger pulse used by the mod. It can accept a potentiometer to change the playback speed (1/4x, 1/2x, 2x, 4x ....). An LED is used to show each pulse.
 
# Reference

[https://synthhacker.blogspot.com/2014/02/arpeggiator-fun-my-midi-to-trigger.html](https://synthhacker.blogspot.com/2014/02/arpeggiator-fun-my-midi-to-trigger.html)


