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
        * [Actions](#actions)
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

1. **New Automation Sequence** - Creates a new automation sequence
2. **Load Automation Sequence** - Loads a saved automation sequence .json file

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

## Automations
Automations for both triggers and actions are structured like this:

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/03-Automation.png" | relative_url }}' alt='An automation' width="60%">
</p>

The current active automation will be highlighted green.

1. **Visibility Button** - Toggles the visibility of the automation.
    * The automation will still run when hidden.
2. **Enable Button** - Toggles if the automation is enabled.
    * The automation will not run when disabled.
3. **Automation Name** - The automation's name.
4. **Duplicate Button** - Duplicates the automation.
5. **Delete Button** - Deletes the automation.
6. **Move Up Button** - Moves the automation up in the sequence.
7. **Move Down Button** - Moves the automation down in the sequence.
8. **Automation Contents** - The contents of the automation. This is different for each type of automation.

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
    * **Battery Percentage** - The battery percentage is compared to a user-defined value.

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

#### Pin Trigger
The manual trigger provides a button for the user to press to manually progress the sequence.

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Trigger-Manual.png" | relative_url }}' alt='Manual Trigger' width="60%">
</p>

### Actions

## Examples
