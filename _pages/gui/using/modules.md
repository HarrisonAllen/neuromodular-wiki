---
layout: topic
title: Using the GUI - Modules
permalink: /gui/using/modules/
previous: /gui/using/
base: /gui/
next: /gui/using/pins/
---

## Quick links
* [Main Window]({{ "/gui/using/" | relative_url }})
* On this page:
    * [Operation Example](#operation-example)
    * [Module Sidebar](#module-sidebar)
    * [Module Controllers](#module-controllers)
    * [Module Graphs](#module-graphs)
    * [Real Data Example](#real-data-example)
* [Pin Control]({{ "/gui/using/pins/" | relative_url }})
* [Automation Sequence]({{ "/gui/using/automation/" | relative_url }})

## Operation Example
Here is what a connected module with two LEDs stimulating and one NTC recording temperature looks like:

<p align="center">
    <img src='{{ "/assets/img/gui/using/modules/OperationExample.gif" | relative_url }}' alt='Example of real data' width="80%">
</p>

## Module Sidebar
The Module Sidebar provides basic information on connected modules and allows for a few basic actions.

<p align="center">
    <img src='{{ "/assets/img/gui/using/modules/01-ModuleSidebar.png" | relative_url }}' alt='The module sidebar' width="60%">
</p>

1. **Visibility Button** - Toggles the visibility of the module.
    * This will hide/show the module and its graph.
2. **Module Name** - Displays the module's name.
    * The name contains the module number and the module type. There are two module types:
        * P for PWM - Only supports pulse-width modulation at 3.3v.
        * A for Analog - Allows for voltage output from 0v-3.3v
    * You can hover over the name to see which serial port the module is connected through.
3. **Connection Status** - Shows whether the module is connected via Bluetooth or not.
4. **Stop Everything** - Stops every pin on the module.
5. **Sync** - Syncs multiple modules.
    * When two or more modules are synced, any command that is sent to one module is sent to the others.
    * For example, starting Pin 1 on one module will start Pin 1 on al synced modules.
    * Be careful when syncing PWM and Analog modules, as PWM settings will not work on an Analog module, and vice versa.
6. **Remove Module** - This will remove the module from the GUI.
    * This is useful if you have a module that you previously connected, but is now disconnected and you do not need it on the GUI anymore.
    * Disconnected modules will reappear if they are powered on or send a message to the GUI.
    
## Module Controllers
The Module Controllers allow for control of multiple modules.

<p align="center">
    <img src='{{ "/assets/img/gui/using/modules/02-Modules.png" | relative_url }}' alt='The module controller' width="80%">
</p>

1. **Module Title** - Displays the module name and the module type.
2. **Connection Status** - Shows whether the module is connected via Bluetooth or not.
    * If the module is disconnected, the controller will turn red such as Module 3.P on the right. The [module's graph](#module-graphs) will also turn red.
3. **Battery Percentage** - Shows the approximate battery percentage remaining on the module.
    * You can hover over the icon for a more detailed percentage and battery voltage measurement.
    * The battery percentage is updated every 5 seconds.
4. **Reset** - Resets the module
5. **Stop Everything** - Stops every pin on the module.
6. **Open Config** - Opens a saved module config file.
    * NOTE: You can use a single config file for other modules of the same type. However, you cannot mix types, such as using a PWM config file for an Analog module.
7. **Save Config** - Saves the current module and pin settings as a .json config file.
8. [**Pin Control**]({{ "/gui/using/pins/" | relative_url }}) - These control individual pins on the module.

## Module Graphs
The Module Graphs display data from the modules.

<p align="center">
    <img src='{{ "/assets/img/gui/using/modules/03-ModuleGraphs.png" | relative_url }}' alt='The module graphs' width="80%">
</p>

1. **Module Name** - Displays the module's name.
2. **Module Graph** - Data and events are shown here ([see the example below](#real-data-example)).
3. **Export Data** - Exports the data for this module.
    * The data will be automatically exported into a folder, so you will have to select the directory where you want that folder to be created.
4. **Clear Data** - Clears all recorded data for that module.