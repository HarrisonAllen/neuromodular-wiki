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
* [**Blue/Green/Red LED**](#led-pin-controller) - Provides repeating pulse-rest waveforms for optogenitic stimulation.
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

## LED Pin Controller

<p align="center">
    <img src='{{ "/assets/img/gui/using/pins/02-LEDPin.png" | relative_url }}' alt='LED Pin Controller' width="60%">
</p>

1. **LED Status and Manual Control Button** - Displays LED status and allows for manual control.
    * Clicking this button will toggle the LED pin on and off.
    * The button will automatically update to reflect the status of the LED pin on the module. These statuses are:
        * **Off** - LED is completely off
            <p align="center">
                <img src='{{ "/assets/img/gui/using/pins/02a-LEDPinOff.png" | relative_url }}' alt='LED Pin Off'>
            </p>
        * **On** - LED is completely on (at the duty cycle/voltage set in the settings)
            <p align="center">
                <img src='{{ "/assets/img/gui/using/pins/02b-LEDPinOn.png" | relative_url }}' alt='LED Pin On'>
            </p>
        * **Pulsing** - LED is currently pulsing on and off(according to the waveform set in the settings)
            <p align="center">
                <img src='{{ "/assets/img/gui/using/pins/02c-LEDPinPulsing.png" | relative_url }}' alt='LED Pin Pulsing'>
            </p>
        * **Resting** - LED is currently off and resting (for a duration defined by the waveform set in the settings)
            <p align="center">
                <img src='{{ "/assets/img/gui/using/pins/02d-LEDPinResting.png" | relative_url }}' alt='LED Pin Resting'>
            </p>
2. **Pulse Selection Radio Buttons** - Switch between two pulse waveforms as defined in the settings.
    * This allows for quickly switching between two different waveforms.
3. **Start** - Starts the current LED pulse waveform.
4. **Stop** - Stops the current LED pulse waveform.
    * Once stopped, the LED pin will turn off.
5. [**Settings**](#led-pin-settings) - Settings for the LED pin.
6. **Graph Display Toggle** - Toggles the visibility of the LED pin on the module's graph.
    * This can help declutter the graph by hiding unnecessary data.

## LED Pin Settings

<p align="center">
    <img src='{{ "/assets/img/gui/using/pins/03-LEDPinSettings.png" | relative_url }}' alt='LED Pin Settings' width="80%">
</p>

1. **Pulse 1/2 Selection** - For configuring two different pulses.
    * You can configure two LED pulse waveforms per pin. You can select which one is being applied using the `Pulse Selection Radio Buttons` in the LED Pin Controller.
2. **LED Intensity** - Sets the intensity of the LED.
    * You can either enter a value manually or adjust it using the slider.
    * The intensity is defined as follows:
        * For PWM modules, it is the duty cycle for the LED and ranges from 0-100%. The voltage is always 3.3v.
        * For Analog modules, it is the voltage applied to the LED and ranges from 0-3.3v.
3. **Live Preview** - Checking this will turn on the LED pin at the current intensity.
    * Changes to the intensity will be reflected on the LED pin in real time.
4. **Pulse Duration (ms)** - The duration of the pulse waveform.
5. **Rest Duration (ms)** - The duration of the rest between pulse waveforms.
6. **Pulse On Duration (ms)** - The duration the LED pin is on before switching off during the pulse waveform.
7. **Pulse Off Duration (ms)** - The duration the LED pin is off before switching on during the pulse waveform.
8. **LED Testing Lower Voltage (V)** - The lower voltage bound for LED testing.
    * A tested voltage lower than this bound indicates that there is a short in the circuit.
9. **LED Testing Upper Voltage (V)** - The upper voltage bound for LED testing.
    * A tested voltage higher than this bound indicates that there is a break in the circuit.
10. **Automatic LED Testing Checkbox** - Check this to enable automatic testing.
11. **Automatic LED Testing Frequency (minutes)** - The duration between automatic tests.
12. **Manual Test Button** - Tests the LED pin for shorts or breaks.
    * The test will measure the voltage drop across the LED. 
    * The expected result should be the forward voltage of the LED, but various factors can change that slightly. Therefore there is an acceptable range that can be defined to gauge whether a voltage registers as a short, break, or OK.
    * Here is an example of an "OK" result from testing:
        <p align="center">
            <img src='{{ "/assets/img/gui/using/pins/03a-LEDPinTest.png" | relative_url }}' alt='LED Pin Test - OK' width="60%">
        </p>
    * Failed tests will report either a short or a break.


Notes:
* Make a note that delta mode does not allow for batching data, aka record slower