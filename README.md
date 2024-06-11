# WavTrigger Drum Machine Interface with Arduino
This project turns an Arduino Nano into an interface to make a drum machine using the Robertsonics/Sparkfun WavTrigger board (the OG one)


Demo video here: 

### Features:
- Stereo 44.1 KHz 16 bit CD quality audio
- 16 notes polyphony
- MIDI In 
- Sidechain Out
- Up to 10 drum kits can be saved in the Arduino EEPROM and can be recalled from the "Load Kit" menu

### Overview

For this module, I made a really simple menu, with different sections:

- **Play Kit**

This is where you can make the module sound by feeding MIDI notes to it.
Standard drum MIDI mapping is used.

- **Drum Kit**

Here you can select the samples for the drum machine, from a minimum of 0 (no sample selected) to a maximum of 2048 (maximum number of samples supported by the Wavtrigger board)

- **Sidechain Out**

Here you can select which drum out will be your sidechain out, that can be used as an input when using compressor and/or ducker modules

- **Save Kit**

This is the menu section where you can save your kits, select one of the 10 kits and push select. Your kit will be saved in the EEPROM of the Arduino

- **Load Kit**

Here is where you can load your saved kits.
There's also another option called "Wipe All" which deletes all the saved kits.

## BOM
- 1 x Robertsonics/Sparkfun WavTrigger board (the first version)
- 1 x SD Card (I used a 16 GB one)
- 1 x Arduino Nano
- 1 x SSD1306 128x64 OLED Screen
- 3 x 3.5mm female mono jacks (Out L, Out R and Sidechain Out)
- 1 x 3.5mm female stereo TRS jack (MIDI In, a standard 5 pin din can be used as well)
- 3 x NO momentary push buttons
