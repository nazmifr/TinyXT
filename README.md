# TinyXTConverter

Minimal firmware and hardware schematics to build a working tiny PS/2 keyboard converter 

PC -> XT or AT (PS/2 & DIN5)

This project is available as an affordable kit or finished product that ships worldwide: [buy to support my work]()

![Mockup of the converter](https://raw.githubusercontent.com/nazmifr/TinyXT/master/converter_mockup.jpg)

Or you can build it yourself! It's not that hard no worries!

Using this piece of gear you'll be able to use a normal PS/2 keyboard on your old machines such as:

- Pentium 1 machines 286 / 386 / ...
- Amstrad PC1512, PC4086, PC5086 
- Commodore Amiga 1000 / 2000 Computers
- Old Bull Micral, Goupil, Olivetti, Thomson, IBM ... computers

Made possible by:

[techpaul's ps/2 advanced library](https://github.com/techpaul/PS2KeyAdvanced)

[PJRC's ps/2 library](https://www.pjrc.com/teensy/td_libs_PS2Keyboard.html),

[djsadeepa's instructables on interfacing a PS/2 keyboard and an arduino](https://www.instructables.com/id/Connect-PS2-Keyboard-to-Arduino/) 

[Pedro Umbelino Hackaday article on the old PIC solution](https://hackaday.com/2017/01/21/attoxtkeyboard/)

[kesrut software implementation on Arduino ATMega/ATTiny platform](https://github.com/kesrut/pcxtkbd)

& [Kicad's creators and contributors (CERN)](https://www.kicad-pcb.org/)


BOM:
- Arduino (eg: Nano) or ATTiny85 + IC Socket (ATTiny45 may be compatible)
- Breadboard or PCB
- DIN5 or PS/2 male connector (for the XT PC eg: a mouse or keyboard cable)
- PS/2 or USB female connector (for the keyboard)
- Cables/Jumpers if breadboard

# Testing your USB keyboard with PS/2 capabilities (optional)

If you have an USB keyboard, follow this pinout schematic to connect it to the duino/PCB.

There is a dependency which is the ```PS2Keyboard.h``` library.

You can then test that the communication is occuring with the script ```PS-2_Tester.ino``` 

You may copy the code directly from [here](https://raw.githubusercontent.com/nazmifr/TinyXT/master/PS-2_Tester.ino)

(open Tools>Serial Monitor to see the key presses)

Pins for the KB tester:
D3 = Data
D8 = Clock
5V = 5V
GND = GND

/!\ This converter uses a microcontroller that doesn't have USB Host capabilities, thus it will be unable to convert an USB keyboard that doesn't have legacy protocol fallback to PS/2 (many commercial USB keyboards have this feature).

See [this]() project for an USB to AT Keyboard converter. (it does USB -> Apple ADB as well :p)

Tested on Arduino Nano. Adapt accordingly.

Numlock and Capslock are not implemented on this test script, no worries!

# Arduino prototype

Once you've tested your keyboard, you can take it to the next level: creating a prototype converter. Considering the price of an arduino these days (<5€) this is a perfectly okay solution compared to the converters currently available that cost between 25-30€ for less functionality (the arduino can be reused in another project)

I strongly advise reusing old connectors for the build as well as avoiding to use a breadboard, flying wire mounting is perfectly fine for such a low voltage, low current, low speed project.

The only con of using an arduino is the power consumption that goes from 5mW to 150mW, it should be fine in most cases but for some really old computers, a more finely engineered setup might be preferable.



# Embedded active converter

You want to build your own version of TinyXT, well you CAN! (you can even sell them if you want to!)

## BOM
- Attiny85
- PCB
- DIN5 or minidin6 male connector (or cable, can be salvaged from old electronics)
- minidin6 or USB female connector (can be salvaged)
- DIP8 IC socket

- USB to Serial converter (CH340, FTDI, ...), must support 5V Levels such as the advertised CH340
- Some female-female jumper leads

## Programming the attiny
You need to install the board definitions for the AtTiny chip.

Then please download

Pins


# Tutorials for the newbie

Etching a PCB
Setting up the Arduino IDE
Installing an arduino library
Using a breadboard

# Followup projects (coming soon)

Attiny keylogger
Attiny wifi wireless keylogger
PS/2 TO ADB
PS/2 TO A
