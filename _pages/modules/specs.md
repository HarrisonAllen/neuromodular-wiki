---
layout: topic
title: PWM vs Analog
permalink: /modules/specs/
# previous: 
base: /modules/
next: /modules/configuration/
---

## Specifications of the modules

These lightweight modules offer up to three channels of simultaneous stimulation or measurement at ~1kHz and ~100Hz respectively. Up to 4 modules can be connected wirelessly to one of the [blue boards]({{ "/blue-board/" | relative_url }}) at a time, but more blue boards can be connected to a single computer. They can be powered via battery for upwards of 4 hours of constant stimulation depending on battery capacity, and can also be powered via a wired connection for indefinite runtime.

The currently supported applications for the channels include:

* Stimulation control
    * Constant on-off
    * Continuous pulsing waveform with on and off cycles (e.g. optogenetics stimulation) [image of optogenetic waveform]
    * One-shot pulse (e.g. limited duration heating pulse) [image of one shot pulse]
* Data measurement
    * Voltage measurement
    * Resistance measurement
    * Temperature measurement (using an NTC)
    * A delta measured between two pins

The general circuit for the channels is shown here:

[image of circuit]

This can be used not only with a single fiber, but also multiple fibers that connect back to ground. The channels offer flexibility in the arrangement, allowing for total flexibility with fiber design.

Here's a summary of the specs:

|<b># input/output channels</b>|3|
|<b>Max output frequency</b>|1kHz|
|<b>Max input frequency</b>|100Hz|
|<b>Max # connected modules</b>|4 per blue board|
|<b>Continuous stimulation runtime</b>|Up to 4 hours on battery, indefinite when wired|
|<b>Operating voltage</b>|3.3V|
|<b>Source voltage range</b>|3.3V to 5V|
|<b></b>||
|<b></b>||
|<b></b>||
|<b></b>||

## PWM vs Analog

There are two different versions of the modules: PWM (left) and Analog (right).

(insert images of pwm, analog modules side by side, top and bottom)

Here's a brief comparison of the two:

| |PWM|Analog|
|---|---|---|
|<b>Output Mode</b>|[Pulse-width modulation (PWM)](https://en.wikipedia.org/wiki/Pulse-width_modulation)|[Digital-to-analog converter (DAC)](https://en.wikipedia.org/wiki/Digital-to-analog_converter)|
|<b>Output Range</b>|0% to 100% of 3.3V|0V to 3.3V|
|<b>Input Mode</b>|[Analog-to-digital converter (ADC)](https://en.wikipedia.org/wiki/Analog-to-digital_converter)|[Analog-to-digital converter (ADC)](https://en.wikipedia.org/wiki/Analog-to-digital_converter)|
|<b>Input Range</b>|0V to 3.3V|0V to 3.3V|

## Currently supported features:

* 


Maybe a table here or something

Def want some pictures