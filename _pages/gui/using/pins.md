---
layout: topic
title: Using the GUI - Pins
permalink: /gui/using/pins/
previous: /gui/using/modules/
base: /gui/
next: /gui/using/automation/
---

## Quick links
* [Main Window]({{ "/gui/using/" | relative_url }})
* [Module Control]({{ "/gui/using/modules/" | relative_url }})
* On this page:
* [Automation Sequence]({{ "/gui/using/automation/" | relative_url }})

## Pin Selection
There are 4 pins on a module. Each pin will have a corresponding function on the fiber. Use the dropdown to select the corresponding pin type.

<p align="center">
    <img src='{{ "/assets/img/gui/using/pins/01-PinSelection.png" | relative_url }}' alt='Pin Selection' width="60%">
</p>

The available pin types are:
* [**Blue/Green/Red LED**](#led-pin-control) - Provides repeating pulse-rest waveforms for optogenitic stimulation.
    * Blue, red, and green LED controls all function the same. The different color options are available to help distinguish fibers with multiple colors of LEDs.
* [**Heater**](#heater-pin-control) - Provides a one-shot pulse for powering a heating element.
* [**Temperature**](#temperature-pin-control) - Provides NTC temperature recording.
* [**Voltage**](#voltage-pin-control) - Provides voltage application and recording.
* [**Resistance**](#resistance-pin-control) - Provides resistance recording.
* [**Ground**](#ground-pin-control) - Does nothing but shows which pin on the fiber is allocated as ground.

Here's an example of a module that's been set up with the following pin layout:
1. Blue LED
2. Ground
3. Green LED
4. Temperature

<p align="center">
    <img src='{{ "/assets/img/gui/using/pins/01a-FullSelection.png" | relative_url }}' alt='Full pin selection for a module of Blue LED, Ground, Green LED, Temperature' width="60%">
</p>

Notes:
* Make a note that delta mode does not allow for batching data, aka record slower