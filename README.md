# Arduino Satellite

This is based on the superb work by [Mohit Bhoite](https://www.bhoite.com/)

## Setting up the Arduino

Install the arduino example `File -> Examples -> ArduinoISP -> ArduinoISP`

I'm programming the ATTiny85 (ATTINY85V-10PU-ND) using an Arduino UNO... and that is actually a bit of a pain! There are quite a few online tutorials however most of them seem out of date or broken because of updates to the Arduino IDE / ssl certificates at the moment.  

Here my current setup 26 December 2023

- Arduino IDE 2.2.1
- https://github.com/SpenceKonde/ATTinyCore

In order to install the ATTinyCore board configuration I needed to follow the details in [this comment](https://github.com/SpenceKonde/ATTinyCore/issues/802#issuecomment-1711422779)

Thankfully the ATTinyCore configuration __does not require you to have a 10 micro-farad capacitor__ like [these instructions](https://www.instructables.com/How-to-Program-an-Attiny85-From-an-Arduino-Uno/)

### Flashing the chip

Pin out guide for ATTiny85:

<img width="999" alt="image" src="https://github.com/jeropaul/arduino_satellite/assets/520985/4eeb926a-4e23-460c-80e3-5199d2788382">

Wiring setup:

<img width="312" alt="image" src="https://github.com/jeropaul/arduino_satellite/assets/520985/717b906d-6a0e-408c-b388-93f8f7884107">

When flashing the chip make sure to flash using the __INTERNAL__ clock source. Otherwise the chip requires an external crystal oscillator and you __cannot re-flash__ the chip without one.

These are the settings I'm using at the moment:

<img width="841" alt="Screen Shot 2023-12-26 at 10 14 04 am" src="https://github.com/jeropaul/arduino_satellite/assets/520985/d34df3c9-fc34-489c-9092-afd20b0297fc">

Then it is just about pressing `Tools -> Burn Bootloader`

## Programming the ATTiny85

This one was also really annoying! there is a handy upload button <img width="463" alt="Screen Shot 2023-12-26 at 10 16 22 am" src="https://github.com/jeropaul/arduino_satellite/assets/520985/26745020-0b4e-4f7e-bb7b-144c8e044aa6"> but it does not work!

To upload your program you need to navigate to sketch -> Upload using programmer 

<img width="304" alt="image" src="https://github.com/jeropaul/arduino_satellite/assets/520985/767ca49d-d04a-4417-9963-b9d542cb6825">

After that I've still found it hit and miss to successfully upload the program with weird intermittent issues but it works well enough...


