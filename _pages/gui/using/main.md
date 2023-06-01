---
layout: topic
title: Using the GUI
permalink: /gui/using/
previous: /gui/installing/
base: /gui/
next: /gui/using/modules/
---

## Quick links
* On this page:
    * [Getting Started](#getting-started)
        * [Connecting a Module](#connecting-a-module)
    * [Port Manager](#port-manager)
    * [Logs](#logs)
    * [Settings](#settings)
* [Module Control]({{ "/gui/using/modules/" | relative_url }})
* [Pin Control]({{ "/gui/using/pins/" | relative_url }})
* [Automation Sequence]({{ "/gui/using/automation/" | relative_url }})

## Getting Started
<p align="center"><div class="youtube-video-container"><iframe width="1903" height="826" src="https://www.youtube.com/embed/v7-nl3x5ur4" title="Neuromodular - Getting Started" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe></div></p>
1. [Install the Neuromodular GUI]({{ "/gui/installing/" | relative_url }})
2. Launch Neuromodular

This is what the GUI looks like when you launch it:

<p align="center">
    <img src='{{ "/assets/img/gui/using/01-MainMenu.png" | relative_url }}' alt='Main menu on first launch' width="80%">
</p>

1. [Port Manager](#port-manager)
2. [Module Sidebar]({{ "/gui/using/modules/" | relative_url }})
3. [Automation Sequences]({{ "/gui/using/automation/" | relative_url }})
4. [Modules]({{ "/gui/using/modules/" | relative_url }})
5. [Module Graphs]({{ "/gui/using/modules/" | relative_url }})

### Connecting a Module
1. Plug the blue dev board into your computer
2. Select the COM port corresponding to the blue dev board from the [Port Manager](#port-manager) dropdown
3. Power on the module
4. The module should automatically show up like this:

<p align="center">
    <img src='{{ "/assets/img/gui/using/03-ModuleConnected.png" | relative_url }}' alt='GUI with module connected' width="80%">
</p>

**Notes**
* You can connect up to 16 modules per blue dev board. To increase this number, you can connect multiple blue dev boards at once.


## Port Manager
The port manager handles the connection between the GUI and serial devices connected to this computer. Access to the Logs window and Settings menu are found here.

<p align="center">
    <img src='{{ "/assets/img/gui/using/02-PortManager.png" | relative_url }}' alt='The port manager' width="60%">
</p>

1. **Port number**
2. **Port selection dropdown** - Select the COM port for the connected serial device. 
    * This will refresh the list of connected devices whenever you click on the dropdown. 
    * To check that you are selecting the correct port for the blue dev board, you can do the following:
        1. Make sure the blue dev board is disconnected
        2. Click on the port dropdown and make note of the listed ports
        3. Plug the blue dev board into your computer
        4. Click on the port dropdown, and select the new COM port that appears
3. **Add port** - Adds a new port.
    * This can be used if you wish to connect another serial device. Examples of other devices include more blue dev boards or an Arduino microcontroller. 
    * Note that any device you connect will need a Baud Rate of 115200.
4. **Remove port** - Removes this port.
5. [**Show Logs**](#logs) - Opens the Logs window.
6. [**Settings**](#settings) - Opens the Settings menu.

## Logs
The Logs window displays messages sent to and received from connected serial devices.

<p align="center">
    <img src='{{ "/assets/img/gui/using/04-Logs.png" | relative_url }}' alt='Logs window' width="60%">
</p>

1. **Manual command entry** - Allows for entry of manual commands to send to serial devices.
2. **Manual command send** - Sends the entered manual command.
3. **Clear logs** - Clears all of the recorded logs.
4. **Export logs** - Exports the logs to a .csv file
5. **Show all logs** - Enable to show all logs.
    * By default, the logs window will only display errors. Enabling this will show all logs that come in from connected serial devices.

A serial message is broken down as follows:
* a. Timestamp of the message
* b. Serial port the message is to/from
* c. Direction of the message
    * `=>` - Message sent to serial device
    * `<=` - Message received from serial device
* d. Message

## Settings
The Settings menu contains application wide settings. Currently it only handles module graph display settings.

<p align="center">
    <img src='{{ "/assets/img/gui/using/05-Settings.png" | relative_url }}' alt='Settings menu' width="70%">
</p>

1. **Graph height** - The height of the module graph, in pixels.
2. **Graph width** - The width of the module graph, in pixels.
3. **Graph time range** - How many seconds into the past to display on the graph.
    * For example, to display all data from 30 seconds ago to now, you would set this value to 30.
4. **Graph time units** - The units for the x axis of the graph.
    * The availabe units are:
        * Real Time - The time that the data point was recorded.
        * Seconds - Seconds since the first data point was recorded.
        * Milliseconds - Milliseconds since the first data point was recorded.