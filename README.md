# TinyXTConverter

Minimal firmware and hardware schematics to build a working tiny PS/2 keyboard converter 

PC -> XT or AT (PS/2 & DIN5)

This project is available as a kit or finished product that ships worldwide:

Or you can build it yourself! It's not that hard no worries!

Using this piece of gear you'll be able to use a normal PS/2 keyboard on your old machines such as:

- Pentium 1 machines 286/386/...
- Amstrad PC1512, PC4086, PC5086 
- Old Bull Micral, Olivetti, ... computers

Made possible by:

PJRC's [ps/2 library](https://www.pjrc.com/teensy/td_libs_PS2Keyboard.html),

[djsadeepa's instructables](https://www.instructables.com/id/Connect-PS2-Keyboard-to-Arduino/) 
[Pedro Umbelino Hackaday article on the old PIC solution](https://hackaday.com/2017/01/21/attoxtkeyboard/)
[kesrut software implementation on Arduino ATMega/ATTiny platform](https://github.com/kesrut/pcxtkbd)
& [Kicad's creators and contributors (CERN)](https://www.kicad-pcb.org/)


BOM:
- Arduino (eg: Nano) or ATTiny85 + IC Socket (ATTiny45 may be compatible)
- Breadboard or PCB
- DIN5 or PS/2 male connector (for the XT PC eg: a mouse or keyboard cable)
- PS/2 or USB female connector (for the keyboard)
- Cables/Jumpers if breadboard

# Testing your keyboard PS/2 capabilities

If you have an USB keyboard, follow this pinout schematic to connect it to the duino/PCB.

You can then test that the communication is occuring with the script ```PS-2_Tester.ino```

/!\ This converter uses a microcontroller that doesn't have USB Host capabilities, thus it will be unable to convert an USB keyboard that doesn't have legacy protocol fallback to PS/2 (many commercial USB keyboards have this feature).

See this project for an USB to AT Keyboard converter. (it does USB -> Apple ADB as well :p)

# Arduino prototype

# Embedded active converter

# 
