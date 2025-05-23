# WavTrigger Drum Machine Interface with Arduino
This project turns an Arduino Nano into an interface to make a drum machine using the Robertsonics/Sparkfun WavTrigger board (the OG one)

Find the latest version in the ![Releases](https://github.com/mexbeb/wavtrigger-dmi/releases) section!

###  THE WAVTRIGGER DMI PROJECT RANKED 2ND IN THE ELECTROMAKER OF THE MONTH CONTEST FOR JUNE 2024!
https://www.electromaker.io/blog/article/electromaker-of-the-month-june-2024-winners

![Wav_DMI](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/cac4b671-b62f-4e09-94f0-0c97a3f3e7d3)

Demo video here: https://youtu.be/mT6QcL0XK70

### Features:
- Stereo 44.1 KHz 16 bit CD quality audio
- 16 drum kit pieces
- 14 notes polyphony
- MIDI In 
- Sidechain Out
- Up to 10 drum kits can be saved in the Arduino EEPROM and can be recalled from the "Load Kit" menu

## Overview

The interface is really simple, I made a menu (inspired by upiir's work) with different sub-menus

![1](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/43dc5a1d-29b4-4484-9105-4034e073bfdb)
![2](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/c74dcdf4-4c33-4803-93ab-7647fb2b753b)

### **Play Kit**

![3](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/211c1f20-2ee7-469a-95f4-d464966da3e1)

This is where you can make the module play samples by feeding MIDI notes to it.
Standard drum MIDI mapping is used.
```
  Kick     //C1 --> 36
  Snare    //D1 --> 38
  Clap     //Eb1 --> 39
  C Hat    //F#1 --> 42
  O Hat    //Bb1 --> 46
  Tom 1    //D2 --> 50 (Hi Tom)
  Tom 2    //B1 --> 47 (Low-Mid Tom)
  Tom 3    //G1 --> 43 (Hi Floor Tom)
  Crash    //C#2 --> 49
  Ride     //Eb2 --> 51
  Cowbell  //Ab2 --> 56
  Conga    //Eb3 --> 63 (Hi Conga)
  Flexi 1  // --> 82
  Flexi 2  // --> 83
  Flexi 3  // --> 84
  Flexi 4  // --> 85
```
### **Drum Kit**

![4](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/d753f4b5-28df-4fa0-8e70-22c4514fe39a)
![5](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/4ce879d4-5eed-4c3f-b5bd-bb6de4e7ca45)

Here you can select the samples, from a minimum of 0 (no sample selected) to a maximum of 2048 (maximum number of samples supported by the Wavtrigger board)

### **Sidechain Out**

![6](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/d6c77858-7176-4d1b-9b8b-afe3b40737fa)

Here you can select which drum out will be your sidechain out. This can be used as an input for compressor and/or ducker modules

### **Save Kit**

![7](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/f2504d5f-56a5-48ab-8df2-efe1168cc384)
![8](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/a169c9ef-ccc4-4dcc-933e-16dc2672d88f)

This is the menu section where you can save your kits, choose one of the 10 kits and push "Select". Your kit will be saved in the EEPROM of the Arduino

### **Load Kit**
 
![9](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/8644990a-e175-4908-9676-31b1f709280a)
![10](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/2d407977-800d-4293-afcc-8d6d880246ac)


Here is where you can load your saved kits.
There's also another option called "Wipe All" which deletes all the saved kits.

![11](https://github.com/mexbeb/wavtrigger-dmi/assets/74735686/5bd9f84c-5cba-49f1-8aa5-cae1ae6f8d1e)

## BOM
- 1 x Robertsonics/Sparkfun WavTrigger board (the first version)
- 1 x SD Card (I used a 16 GB one)
- 1 x Arduino Nano
- 1 x SSD1306 128x64 OLED Screen
- 3 x 3.5mm female mono jacks (Out L, Out R and Sidechain Out)
- 1 x 3.5mm female stereo TRS jack (MIDI In, a standard 5 pin din can be used as well)
- 3 x NO momentary push buttons
- 1 x 6N138 Optocoupler
- 1 x 220 Ohm Resistor
- 1 x 4.7KOhm Resistor
- 1 x 1KOhm Resistor
- 1 x 1N914 Diode
- 2 x BAT43 diodes (these two combined with the 1K resistor are used to protect the Arduino's pin, as in Hagiwo's circuits)

Thanks to:

- upiir, for the menu implementation -> https://github.com/upiir/arduino_oled_menu
