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

### Actions

## Examples
