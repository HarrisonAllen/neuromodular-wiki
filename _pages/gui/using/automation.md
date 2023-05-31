---
layout: topic
title: Using the GUI - Automation
permalink: /gui/using/automation/
previous: /gui/using/pins/
base: /gui/
# next:
---

## Quick links
* [Main Window]({{ "/gui/using/" | relative_url }})
* [Module Control]({{ "/gui/using/modules/" | relative_url }})
* [Pin Control]({{ "/gui/using/pins/" | relative_url }})
* On this page:
    * [Automation Sequence Introduction](#automation-sequence-introduction)
    * [Automation Sequence](#automation-sequence)
    * [Automations](#automations)
        * [Triggers](#triggers)
            * [Serial Messsage Trigger](#serial-message-trigger)
            * [Module Trigger](#module-trigger)
            * [Pin Trigger](#pin-trigger)
            * [Manual Trigger](#manual-trigger)
        * [Actions](#actions)
            * [Time Delay](#time-delay-action)
            * [Module](#module-action)
            * [Pin](#pin-action)
            * [Alert](#alert-action)
            * [Email](#email-action)
    * [Examples](#examples)

## Automation Sequence Introduction
Automation sequences allow for automated control of modules based on various triggers. For example, you could perform the following sequence using automations:
1. Trigger: Serial message "TTL Pulse 1" received
2. Action: Start stimulation on Module 3.P Pin 1 (Blue LED)
3. Action: Delay 5 seconds
4. Action: Stop stimulation on Module 3.P Pin 1 (Blue LED)
5. Repeat

Here is an example of a simple automation sequence to show how it looks when a sequence is running:
1. Trigger: Manual
2. Action: Delay 250 ms
3. Action: Delay 500 ms
4. Action: Delay 750 ms
5. Repeat/Don't repeat (depending on repeat setting)

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Sequence Loop Example.gif" | relative_url }}' alt='Example of automation sequence' width="60%">
</p>

## Automation Sequence Manager

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/01-MainButtons.png" | relative_url }}' alt='The automation sequence manager' width="60%">
</p>

1. **New Automation Sequence** - Creates a new automation sequence.
2. **Load Automation Sequence** - Loads a saved automation sequence .json file

[Back to top](#)

## Automation Sequence

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/02-AutomationSequence.png" | relative_url }}' alt='The automation sequence' width="60%">
</p>

1. **Sequence Name** - Edit this to change the name of the sequence.
2. **Visibility Button** - Toggles the visibility of the sequence.
    * The sequence will still run when hidden.
3. **Enable Button** - Toggles if the sequence is enabled.
    * The sequence will not run when disabled.
4. **Next Button** - Skips to the next automation in the sequence.
5. **Repeat Button** - Toggles if the sequence will repeat.
    * When repeat is enabled, the sequence will automatically loop back around to the first automation after the sequence ends.
    * When repeat is disabled, the sequence will stop when the sequence ends. You will have to press the Restart Button in order to restart the sequence.
6. **Restart Button** - Restarts the sequence from the first automation.
7. **Save Button** - Saves the sequence as a .json file.
8. **Delete Button** - Deletes the sequence.
9. **Add Trigger Button** - Opens the Add Trigger window.
    * Triggers are automations that wait for specific events.
    * The available triggers are:
        * [**Serial Message**](#serial-message-trigger) - Waits for a user-defined message from one of the connected serial devices.
        * [**Module**](#module-trigger) - Waits for module-specific events.
        * [**Pin**](#pin-trigger) - Waits for pin-specific events.
        * [**Manual**](#manual-trigger) - Waits for the user to press the button.
10. **Add Action Button** - Opens the Add Action window.
    * Actions are automations that perform specific actions.
    * The available actions are:
        * [**Time Delay**](#time-delay-action) - Pauses the sequence for a user-defined amount of time before continuing to the next automation.
        * [**Module**](#module-action) - Executes module-specific actions.
        * [**Pin**](#pin-action) - Executes pin-specific actions.
        * [**Alert**](#alert-action) - Pops up an alert with a user-defined message.
        * [**Email**](#email-action) - Sends an email, can include module data.

[Back to top](#)

## Automations
Automations for both triggers and actions are structured like this:

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/03-Automation.png" | relative_url }}' alt='An automation' width="60%">
</p>

The current active automation will be highlighted green.

1. **Visibility Button** - Toggles the visibility of the automation.
    * The automation will still run when hidden.
2. **Enable Button** - Toggles if the automation is enabled.
    * The automation will be skipped when disabled.
3. **Automation Name** - The automation's name.
4. **Duplicate Button** - Duplicates the automation.
5. **Delete Button** - Deletes the automation.
6. **Move Up Button** - Moves the automation up in the sequence.
7. **Move Down Button** - Moves the automation down in the sequence.
8. **Automation Contents** - The contents of the automation. This is different for each type of automation.

[Back to top](#)

### Triggers

#### Serial Message Trigger
The serial message trigger listens to all of the serial devices connected through the [Port Manager]({{ "/gui/using/#port-manager" | relative_url }}). The automation is triggered when a serial message matches the user-defined message.

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Trigger-Serial.png" | relative_url }}' alt='Serial Message Trigger' width="60%">
</p>

**Parameters**
* **Message** - The user-defined message this trigger is listening for
* **Match type** - The way the serial message has to match the user-defined message.
    * **Exact** - The serial message is exactly the same as the user-defined message.
        * E.g. "TTL Pulse 1" exactly matches "TTL Pulse 1"
    * **Contains** - The serial message contains the user-defined message.
        * E.g. "TTL Pulse 1" contains "Pulse"
    * **Starts with** - The serial message starts with the user-defined message.
        * E.g. "TTL Pulse 1" starts with "TTL"
    * **Ends with** - The serial message ends with the user-defined message.
        * E.g. "TTL Pulse 1" ends with "Pulse 1"

[Back to top](#)

#### Module Trigger
The module trigger listens for certain module-specific events. This can be for a single module or any connected module.

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Trigger-Module.png" | relative_url }}' alt='Module Trigger' width="60%">
</p>

**Parameters**
* **Module** - The connected module to listen to.
    * Select `Any` to listen to all of the connected modules.
* **Events**
    * **Connected** - The module was connected via Bluetooth.
    * **Disconnected** - The module was disconnected via Bluetooth.
    * **Reset** - The module was reset.
    * **Battery Percentage** - The module's battery percentage is compared to a user-defined value.

[Back to top](#)

#### Pin Trigger
The pin trigger listens for certain pin-specific events. This can be for a single module or any connected module.

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Trigger-Pin.png" | relative_url }}' alt='Pin Trigger' width="60%">
</p>

**Parameters**
* **Module** - The connected module to listen to.
    * Select `Any` to listen to all of the connected modules.
* **Pin** - The module's pin to listen to.
* **Pin Types**
    * **Blue/Green/Red LED**
        * **Start** - The LED pulse waveform has started.
        * **Stop** - The LED pulse waveform has stopped.
        * **Pulse** - The pulsing segment of the LED pulse waveform has started.
        * **Rest** - The resting segment of the LED pulse waveform has started.
        * **On** - The LED has turned on manually.
        * **Off** - The LED has turned off manually.
    * **Heater**
        * **Start** - The heater pulse has started.
        * **Stop** - The heater pulse has stopped.
        * **On** - The heater has turned on manually.
        * **Off** - The heater has turned off manually.
    * **Temperature** - The pin temperature is compared to a user-defined value.
    * **Voltage** - The pin voltage is compared to a user-defined value.
    * **Resistance** - The pin resistance is compared to a user-defined value.

[Back to top](#)

#### Manual Trigger
The manual trigger provides a button for the user to press to manually progress the sequence.

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Trigger-Manual.png" | relative_url }}' alt='Manual Trigger' width="60%">
</p>

[Back to top](#)

### Actions

#### Time Delay Action
The time delay action delays the sequence for a user-defined amount of time, then resumes the sequence once complete.

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Action-Time.png" | relative_url }}' alt='Time Delay Action' width="60%">
</p>

**Parameters**
* **Duration (ms)** - The amount of time to delay the sequence.

[Back to top](#)

#### Module Action
Module actions are module specific actions, and can also affect multiple pins at once. This can be for a single module or all connected modules.

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Action-Module.png" | relative_url }}' alt='Module Action' width="60%">
</p>

**Parameters**
* **Module** - The connected module to perform this action on.
    * Select `All` to apply this to all of the connected modules.
* **Actions**
    * **Start Pins** - Starts the selected pins on the module.
    * **Stop Pins** - Stops the selected pins on the module.
    * **Reset** - Resets the module.
    * **Export Data** - Exports the module's data.
        * **Choose folder...** - Choose the folder to export the data to.
    * **Clear Data** - Clears the module's data.

[Back to top](#)

#### Pin Action
Pin actions are pin-specific actions. This can be for a single module or all connected modules.

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Action-Pin.png" | relative_url }}' alt='Pin Action' width="60%">
</p>

**Parameters**
* **Module** - The connected module to perform this action on.
    * Select `All` to apply this to all of the connected modules.
* **Pin** - The module's pin to perform this action on.
* **Pin Types**
    * **Blue/Green/Red LED**
        * **Actions**
            * **Start** - Starts the LED pulse waveform.
            * **Stop** - Stops the LED pulse waveform.
            * **On** - Turns the LED on.
            * **Off** - Turns the LED off.
            * **Apply Settings** - Applies the settings configured by the settings button. See [LED Pin Settings]({{ "/gui/using/pins/#led-pin-settings" | relative_url }}) for more details.
        * **Settings Button** - Opens up a settings menu exclusively for this automation.
        * **PWM/Analog** - Be sure to select the correct module type when using "Apply Settings". This doesn't matter when doing other actions, such as "Start".
    * **Heater**
        * **Actions**
            * **Start** - Starts the heater pulse.
            * **Stop** - Stops the heater pulse.
            * **On** - Turns the heater on.
            * **Off** - Turns the heater off.
            * **Apply Settings** - Applies the settings configured by the settings button. See [Heater Pin Settings]({{ "/gui/using/pins/#heater-pin-settings" | relative_url }}) for more details.
        * **Settings Button** - Opens up a settings menu exclusively for this automation.
        * **PWM/Analog** - Be sure to select the correct module type when using "Apply Settings". This doesn't matter when doing other actions, such as "Start".
    * **Temperature**
        * **Actions**
            * **Start** - Starts recording temperature.
            * **Stop** - Stops recording temperature.
            * **Take Reading** - Makes a single temperature measurement.
            * **Apply Settings** - Applies the settings configured by the settings button. See [Temperature Pin Settings]({{ "/gui/using/pins/#temperature-pin-settings" | relative_url }}) for more details.
        * **Settings Button** - Opens up a settings menu exclusively for this automation.
        * **PWM/Analog** - Be sure to select the correct module type when using "Apply Settings". This doesn't matter when doing other actions, such as "Start".
    * **Voltage**
        * **Actions**
            * **Start** - Starts recording voltage.
            * **Stop** - Stops recording voltage.
            * **Take Reading** - Makes a single voltage measurement.
            * **Apply Settings** - Applies the settings configured by the settings button. See [Voltage Pin Settings]({{ "/gui/using/pins/#voltage-pin-settings" | relative_url }}) for more details.
        * **Settings Button** - Opens up a settings menu exclusively for this automation.
        * **PWM/Analog** - Be sure to select the correct module type when using "Apply Settings". This doesn't matter when doing other actions, such as "Start".
    * **Resistance**
        * **Actions**
            * **Start** - Starts recording resistance.
            * **Stop** - Stops recording resistance.
            * **Take Reading** - Makes a single resistance measurement.
            * **Apply Settings** - Applies the settings configured by the settings button. See [Resistance Pin Settings]({{ "/gui/using/pins/#resistance-pin-settings" | relative_url }}) for more details.
        * **Settings Button** - Opens up a settings menu exclusively for this automation.
        * **PWM/Analog** - Be sure to select the correct module type when using "Apply Settings". This doesn't matter when doing other actions, such as "Start".

[Back to top](#)

#### Alert Action
The alert action pops up an alert with a user-defined message. The sequence will pause until the user dismisses the alert.

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Action-Alert.png" | relative_url }}' alt='Alert Action' width="60%">
</p>

**Parameters**
* **Message** - The message to display in the alert.

[Back to top](#)

#### Email Action
The email action will send an email to specified email addresses and can include the data from all of the modules.

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Action-Email.png" | relative_url }}' alt='Email Action' width="60%">
</p>

**Parameters**
* **From** - The email address the email will be sent from.
    * This must be a Gmail address.
* **App Password** - In order to use the email action, you must [generate an app password](https://support.google.com/accounts/answer/185833?hl=en).
    * Do NOT use your regular password, only a generated app password.
    * Be warned that saving the automation sequence will store the app password in the generated .json file, so be careful not to share automation sequences that contain your app password!
        * I recommend clearing out the "From" and "App Password" fields when sharing an automation sequence that uses an email action.
* **To** - Email addresses that the email should be sent to.
    * You can input multiple email addresses separated by commas (no spaces). For example, "myemail@gmail.com,anotheremail@mit.edu"
    * These email addresses do not need to be Gmail addresses.
* **Subject** - The email's subject line.
* **Body** - The email's body.
* **Send module data** - Check this to send data from every module.
    * This will export the data from every module that is listed, even if they are disconnected.

[Back to top](#)

## Examples
Here I have prepared examples for you to download and try out.

### Send data when battery is low
1. Wait for the module battery to go below 5%
2. Stop all of the pins on the module
3. Send an email notifying that the module has run out of battery, and include the module's data.

[Download `Send data when low on battery.json`]({{ "/assets/files/gui/using/sequence/examples/Send data when low on battery.json" | relative_url }})

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/examples/Send data when low on battery.png" | relative_url }}' alt='Send data when low on battery preview' width="60%">
</p>

[Back to top](#)