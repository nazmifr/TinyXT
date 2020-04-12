# TinyXTConverter

![Mockup of the converter](https://raw.githubusercontent.com/nazmifr/TinyXT/master/converter_mockup.jpg)

Minimal firmware and hardware schematics to build a working tiny PS/2 keyboard converter 

PC -> XT or AT (PS/2 & DIN5)

This project is available as a kit or finished product that ships worldwide:

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

You may copy directly from here:
```
#include <PS2Keyboard.h>

const int DataPin = 8;
const int IRQpin =  3;

PS2Keyboard keyboard;

void setup() {
  delay(1000);
  keyboard.begin(DataPin, IRQpin);
  Serial.begin(9600);
  Serial.println("Keyboard Test:");
}

void loop() {
  if (keyboard.available()) {
    
    // read the next key
    char c = keyboard.read();
    
    // check for some of the special keys
    if (c == PS2_ENTER) {
      Serial.println();
    } else if (c == PS2_TAB) {
      Serial.print("[Tab]");
    } else if (c == PS2_ESC) {
      Serial.print("[ESC]");
    } else if (c == PS2_PAGEDOWN) {
      Serial.print("[PgDn]");
    } else if (c == PS2_PAGEUP) {
      Serial.print("[PgUp]");
    } else if (c == PS2_LEFTARROW) {
      Serial.print("[Left]");
    } else if (c == PS2_RIGHTARROW) {
      Serial.print("[Right]");
    } else if (c == PS2_UPARROW) {
      Serial.print("[Up]");
    } else if (c == PS2_DOWNARROW) {
      Serial.print("[Down]");
    } else if (c == PS2_DELETE) {
      Serial.print("[Del]");
    } else {
      
      // otherwise, just print all normal characters
      Serial.print(c);
    }
  }
}
```

/!\ This converter uses a microcontroller that doesn't have USB Host capabilities, thus it will be unable to convert an USB keyboard that doesn't have legacy protocol fallback to PS/2 (many commercial USB keyboards have this feature).

See this project for an USB to AT Keyboard converter. (it does USB -> Apple ADB as well :p)

# Arduino prototype

# Embedded active converter

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
