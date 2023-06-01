---
layout: topic
title: Modules - Information
permalink: /modules/information/
# previous: 
base: /modules/
next: /modules/assembly/
---

## General Information
|Parameter|Value|
| --- | --- |
|<b># input/output channels</b>|3 (4 pins, 1 reserved for ground)|
|<b>Max output frequency</b>|1kHz|
|<b>Max input frequency</b>|100Hz|
|<b>Max # connected modules</b>|16 per blue dev board (can use multiple blue dev boards for more connections)|
|<b>Continuous stimulation runtime</b>|Up to 4 hours on battery, indefinite when wired|
|<b>Operating voltage</b>|3.3V|
|<b>Minimum voltage supply</b>|3.3V|
|<b>Maximum voltage supply</b>|5V|

## Module Type Differences
<p align="center">
    <img src='{{ "/assets/img/modules/information/Modules01.jpg" | relative_url }}' alt='Top of two modules' width="60%">
</p>
<p align="center">
    <img src='{{ "/assets/img/modules/information/Modules02.jpg" | relative_url }}' alt='Bottom of two modules' width="60%">
</p>

* **PWM Modules** (Pulse-width modulation) - *Module 4.P on the left*
    * PWM modules directly output voltage from the microcontroller.
    * PWM modules can only output at 3.3v, but can apply PWM with varying duty cycles (0-100%) to change the intensity of the output.
    * PWM modules consume less power than Analog modules.
* **Analog Modules** - *Module 23.A on the right*
    * Analog modules output voltage through a combination ADC/DAC.
    * Analog modules can output a range of voltage from 0-3.3v, and can output more power than PWM modules.
    * Analog modules consume more power than PWM modules.

## Fiber Circuits

Each pin on the module has the following circuit layout:

<p align="center">
    <img src='{{ "/assets/img/modules/information/Fiber01.png" | relative_url }}' alt='Fiber circuit' width="60%">
</p>

By soldering the ground jumper on a pin, that pin now routes to ground. If you want to use the pin, you solder the jumper on the "R" side and put on a resistor for that circuit.

You can use any component that can work with this kind of voltage divider circuit. Currently tested components include:
* LEDs
* Resistive heaters
* NTCs (for temperature measuring)

On the modules above, the circuits are configured as follows:

### Module 4.P *(left module)*
|Pin|Fiber Component|Ground Jumper|Resistor Jumper|Resistor|
| --- | --- | --- | --- | --- |
|1|Blue LED||Soldered|0 Ohms|
|2|Ground|Soldered|||
|3|Green LED||Soldered|0 Ohms|
|4|10k Ohm NTC||Soldered|10k Ohms|

### Module 23.A *(right module)*
|Pin|Fiber Component|Ground Jumper|Resistor Jumper|Resistor|
| --- | --- | --- | --- | --- |
|1|Ground|Soldered|||
|2|Heater/Red LED||Soldered|0 Ohms|
|3|10k Ohm NTC||Soldered|10k Ohms|
|4|10k Ohm NTC||Soldered|10k Ohms|

