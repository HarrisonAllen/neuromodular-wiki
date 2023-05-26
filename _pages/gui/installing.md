---
layout: topic
title: Installing the GUI
permalink: /gui/installing/
# previous: 
base: /gui/
next: /gui/using/
---

## Current Installers (v1.2.1b)
* [Download the Windows 10 installer here](https://github.com/HarrisonAllen/neuromodular-wiki/releases/download/v1.2.1b/NeuromodularSetup.exe)

([Jump to changelogs](#changelogs))

## Extra Files
* TTL Detector for Arduino UNO: [TTL-Detector.zip](https://github.com/HarrisonAllen/neuromodular-wiki/files/11567609/TTL-Detector.zip)

## Installing the GUI on Windows
1. Download the most recent installer
2. Run `NeuromodularSetup.exe`
3. In the resulting popup, click on `More info`
    <p align="center">
        <img src='{{ "/assets/img/gui/Warning1_marked.png" | relative_url }}' alt='First warning when installing' width="60%">
    </p>
4. Click on `Run anyway`
    <p align="center">
        <img src='{{ "/assets/img/gui/Warning2_marked.png" | relative_url }}' alt='Second warning when installing' width="60%">
    </p>
5. When prompted with `Do you want to allow this app from an unknown publisher to make changes to your device?`, select `Yes`
6. Follow the steps on the installer
7. You can now launch `Neuromodular`

## Changelogs
* v1.2.1b
    * Fixed a bug where a blank pin action would crash the GUI
    * Changed the serial handler to handle more serial scenarios and avoid crashing on certain malformed messages
    * **Note:** This version of the GUI is required for compatibility with the included dev module firmware update
* v1.2.0b
    * Added automations, which provides architecture to automatically perform certain actions. For example, a serial message from a TTL detector could trigger stimulation on a module.
        * This beta release is missing certain functions, including:
            * Saving and loading automation sequences
            * Sending settings from the "Pin Action" automation
* v1.1.1
    * Added option to change the unit of time on the graphs
    * Changed settings menu layouts to allow for resizing and scrolling, useful for smaller screens
    * Data export now includes both time since first data point and seconds since epoch
* v1.1.0
    * Added low battery notification
    * Added option to auto-test LED fibers every x minutes
        * This will stop and restart stimulation to conduct the test (approx 1ms)
        * LED test now provides timestamp of when result was measured
    * Module panels now turn red on bluetooth disconnect
    * Data export now uses seconds since epoch instead of datestring format

## Previous Installers
* v1.2.0b
    * [Download the Windows 10 installer here](https://github.com/HarrisonAllen/neuromodular-wiki/releases/download/v1.2.0b/NeuromodularSetup.exe)
* v1.1.1
    * [Download the Windows 10 installer here](https://github.com/HarrisonAllen/neuromodular-wiki/releases/download/v1.1.1/NeuromodularSetup.exe)
* v1.1.0
    * [Download the Windows 10 installer here](https://github.com/HarrisonAllen/neuromodular-wiki/releases/download/v1.1.0/NeuromodularSetup.exe)
* v1.0
    * [Download the Windows 10 installer here](https://github.com/HarrisonAllen/neuromodular-wiki/releases/download/v1.0/NeuromodularSetup.exe)

<!-- Basically a link to the GUI (depending on platform), and a guide for installing on each platform. -->