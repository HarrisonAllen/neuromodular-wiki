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
* [**Blue/Green/Red LED**](#led-pin) - Provides repeating pulse-rest waveforms for optogenitic stimulation.
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

## LED Pin

### LED Pin Controller

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
        * **Pulsing** - LED is currently pulsing on and off (according to the waveform set in the settings)
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

### LED Pin Settings

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

### LED Pin Notes
* Do not set any of the Pulse/Rest durations to `0`. This can cause the module to fail.
* To achieve a waveform of just LED on and LED off (no resting) you can do the following:
    * For the example of a repeating 1000ms on, 2000ms off waveform:
        * Pulse Duration: 1000ms
        * Rest Duration: 2000ms
        * Pulse On Duration: 1100ms
        * Pulse Off Duration: 100ms

[Back to top](#)

## Heater Pin

### Heater Pin Controller

<p align="center">
    <img src='{{ "/assets/img/gui/using/pins/04-HeaterPin.png" | relative_url }}' alt='Heater Pin Controller' width="60%">
</p>

1. **Heater Status and Manual Control Button** - Displays Heater status and allows for manual control.
    * Clicking this button will toggle the Heater pin on and off.
    * The button will automatically update to reflect the status of the Heater pin on the module. These statuses are:
        * **Off** - Heater is completely off
            <p align="center">
                <img src='{{ "/assets/img/gui/using/pins/04a-HeaterPinOff.png" | relative_url }}' alt='Heater Pin Off'>
            </p>
        * **On** - Heater is completely on (at the duty cycle/voltage set in the settings)
            <p align="center">
                <img src='{{ "/assets/img/gui/using/pins/04b-HeaterPinOn.png" | relative_url }}' alt='Heater Pin On'>
            </p>
        * **Pulsing** - Heater is currently on and will turn off at the end of the pulse (as defined in the settings)
            <p align="center">
                <img src='{{ "/assets/img/gui/using/pins/04c-HeaterPinPulsing.png" | relative_url }}' alt='Heater Pin Pulsing'>
            </p>
2. **Start** - Starts the Heater pulse.
3. **Stop** - Stops the Heater pulse.
    * Once stopped, the Heater pin will turn off.
4. [**Settings**](#heater-pin-settings) - Settings for the Heater pin.
5. **Graph Display Toggle** - Toggles the visibility of the Heater pin on the module's graph.
    * This can help declutter the graph by hiding unnecessary data.

### Heater Pin Settings

<p align="center">
    <img src='{{ "/assets/img/gui/using/pins/05-HeaterPinSettings.png" | relative_url }}' alt='Heater Pin Settings' width="80%">
</p>

1. **Pulse Duration (ms)** - The duration of the heater pulse before turning off.
2. **Heater Intensity** - Sets the intensity of the Heater.
    * You can either enter a value manually or adjust it using the slider.
    * The intensity is defined as follows:
        * For PWM modules, it is the duty cycle for the Heater and ranges from 0-100%. The voltage is always 3.3v.
        * For Analog modules, it is the voltage applied to the Heater and ranges from 0-3.3v.
3. **Live Preview** - Checking this will turn on the Heater pin at the current intensity.
    * Changes to the intensity will be reflected on the Heater pin in real time.

### Heater Pin Notes
* The Heater pulse will not repeat. If you want to have a repeating cycle, I recommend taking a look at [Automations]({{ "/gui/using/automation/" | relative_url }}).
* Do not set the Pulse duration to `0`. This can cause the module to fail.

[Back to top](#)

## Temperature Pin

### Temperature Pin Controller

<p align="center">
    <img src='{{ "/assets/img/gui/using/pins/06-TemperaturePin.png" | relative_url }}' alt='Temperature Pin Controller' width="60%">
</p>

1. **Temperature Manual Reading Button** - Allows for manual reading of the pin temperature.
    * Clicking this button will request a temperature reading from the module.
    * The manual reading will ignore the delta settings.
2. **Current Temperature Reading (&#176;C)** - Displays the last measured temperature reading from the pin.
3. **Delta Settings** - Designates another pin on the module to measure the temperature delta between. See [Temperature Pin Delta](#temperature-pin-delta) for more information.
4. **Start** - Starts measuring temperature.
5. **Stop** - Stops measuring temperature.
6. [**Settings**](#temperature-pin-settings) - Settings for the temperature pin.
7. **Graph Display Toggle** - Toggles the visibility of the temperature pin on the module's graph.
    * This can help declutter the graph by hiding unnecessary data.

### Temperature Pin Delta

<p align="center">
    <img src='{{ "/assets/img/gui/using/pins/07-TemperaturePinDelta.png" | relative_url }}' alt='Temperature Pin Delta' width="60%">
</p>

1. **Delta Pin Selection** - On the primary pin, select the delta pin to compare.
    * In this example, we use Pin 3 as the primary pin and select Pin 4 as the delta pin.
2. **Temperature Delta Display** - Displays the temperature difference of the primary pin minus the delta pin.
    * In this example, we are seeing: `Pin 3 temperature - Pin 4 temperature` on Pin 3's display.
3. **Temperature Average Display** - Displays the average temperature of the primary pin and the delta pin.
    * In this example, we are seeing: `(Pin 3 temperature + Pin 4 temperature) / 2` on Pin 4's display.
4. **Other Delta Pin Selection** - Do not select anything on the delta pin's delta selection.
    * In this example, we selected Pin 4 as the delta for Pin 3, so we select nothing for Pin 4.

* To start measuring the delta use the `Start` button on the primary pin.
    * In this example, you would press `Start` on Pin 3.

**Delta Notes**:
* The delta and average are only for real time analysis. The recorded data will only include the raw temperature measured by each pin.
* Delta mode only sends one point per batch. Keep this in mind when setting the time between each sample.
* Be sure to synchronize the moving average in the settings on each pin.

### Temperature Pin Settings

<p align="center">
    <img src='{{ "/assets/img/gui/using/pins/06-TemperaturePinSettings.png" | relative_url }}' alt='Temperature Pin Settings' width="80%">
</p>

1. **Moving Average (points)** - The number of points to include in the [moving average](https://en.wikipedia.org/wiki/Moving_average).
    * This helps filter noise and smooth out the data.
    * Higher values will smooth the data more but will take longer to reflect changes in the temperature reading.
    * Lower values will keep the data noisy but will quickly reflect changes in the temperature reading.
    * I recommend a value of 5 to start with.
2. **Time between each sample (ms)** - The time between each temperature measurement.
3. **Points per batch (points)** - The number of points to combine in a single message from the module. 
    * The module measure data at the rate set by `Time between each sample`, and once `Points per batch` points have been measured, the module sends all of them at once.
    * E.g. with 3 `Points per batch`, the module will collect 3 measurements then send them all at once.
    * See the [Temperature Pin Notes](#temperature-pin-notes) for more details.
4. **NTC Beta value @ 25&#176;C** - The fiber NTC's measured beta value at 25&#176;C.
    * The data sheet for the NTC should have an approximation of this, but it's important to measure this value for each NTC that you use to get accurate temperature calculations.
5. **NTC nominal resistance @ 25&#176;C** - The fiber NTC's measured nominal resistance at 25&#176;C.
    * The data sheet for the NTC should have an approximation of this, but it's important to measure this value for each NTC that you use to get accurate temperature calculations.
6. **Module Resistor Value** - The pin resistor used on this module.
    * This resistance is specific to the pin configuration on each module.

### Temperature Pin Notes
* Try to only send data from this pin every 200ms or so. You can send data faster than this, but it may prevent other data from being sent from the module. This is ok for temperature, but could mean that information from other pins (such as LED status) could get lost.
    * For example, if you want to read temperature every 40ms, then increase the `Points per batch` to 5 so that data is only sent after 5 points are measured, i.e. every 200ms.
    * When you are using delta mode, it will only send 1 point per batch regardless of the `Points per batch` setting.
* It's important to set up the NTC and Module parameters correctly to get accurate temperature measurements. If you don't need super accurate data, then you can just use the NTC infromation from its corresponding data sheet.

[Back to top](#)