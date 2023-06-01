---
layout: topic
title: Modules - Power and Batteries
permalink: /modules/battery/
previous: /modules/configuration/
base: /modules/
next: /modules/programming/
---

## Power Options

There are different power options that you can use:
* Attached battery
    * This page covers the process for attaching a battery
    * Charging information can be found [here]({{ "/modules/charger/" | relative_url }})
    * To power on the module, use a jumper to connect the `B` and `+` pins on the module power header.
    <p align="center">
        <img src='{{ "/assets/img/modules/battery/Using01.jpg"  |  relative_url }}' alt='Using' width="60%">
    </p>
* Wired power
    * You can create a wired adapter by removing the middle pin of a 3-pin female header and attaching two wires to the other pins. Those wires can then go to a power supply or a USB cable adapter.
    * To connect the module to a power supply:
        * Set the power supply voltage between 3.3V and 5V, your choice
        * Connect the positive voltage of the supply to `+` on the module power header
        * Connect the ground of the supply to `-` on the module power header
    * To connect to a USB cable adapter:
        * Connect the USB `V+` (5V) to `+` on the module power header
        * Connect the USB `GND` to `-` on the module power header
    <p align="center">
        <img src='{{ "/assets/img/modules/battery/USB01.jpg"  |  relative_url }}' alt='USB' width="40%"><img src='{{ "/assets/img/modules/battery/USB02.jpg"  |  relative_url }}' alt='USB' width="40%">
    </p>
* Removable battery
    * You can create a removable battery board by using an empty module PCB.
        1. Solder the battery to the `+` and `-` battery pads on the bottom of the board (be sure that the battery leads are in the correct polarity!)
        2. Solder a female 3-pin header to the power header pins
        3. Bridge the `B` and `+` pins on the header.
        4. Fold the battery over and secure with epoxy/hot glue
    * Match the + and - on the battery board to the + and - on the module you want to power.
    * You can charge this the same way you'd charge a module.
    <p align="center">
        <img src='{{ "/assets/img/modules/battery/External01.jpg"  |  relative_url }}' alt='External battery' width="40%"><img src='{{ "/assets/img/modules/battery/External02.jpg"  |  relative_url }}' alt='External battery' width="40%">
    </p>
    <p align="center">
        <img src='{{ "/assets/img/modules/battery/External03.jpg"  |  relative_url }}' alt='Extrnal battery' width="60%">
    </p>

## What you'll need:
* An assembled and configured module
* A battery
* Solder paste/solder
* Soldering iron (DO NOT USE A HEAT GUN)
* Tweezers

## Attaching a small battery

### 1. Pre-solder the battery pads on the module

It's very important to apply as little heat to the battery as possible to avoid causing a fire or making the battery explode.

To start, pre-solder the battery pads on the module with a generous amount of solder. This battery has solder on its leads already, which will help a bit.

<p align="center">
    <img src='{{ "/assets/img/modules/battery/Small01.jpg"  |  relative_url }}' alt='Small battery' width="60%">
</p>

### 2. Solder the leads using a soldering iron

Make sure the + and - pads on the module are lined up with the positive and negative leads on the battery.

You'll want to touch the battery leads with the soldering iron for as little time as possible.

Keep the leads towards the edge of the board so that there's enough space to bend it over the board.

<p align="center">
    <img src='{{ "/assets/img/modules/battery/Small02.jpg"  |  relative_url }}' alt='Small battery' width="60%">
</p>
<p align="center">
    <img src='{{ "/assets/img/modules/battery/Small03.jpg"  |  relative_url }}' alt='Small battery' width="60%">
</p>

### 3. Carefully bend the battery over the top of the board

You don't want to break the leads, so be careful with this step!

<p align="center">
    <img src='{{ "/assets/img/modules/battery/Small04.jpg"  |  relative_url }}' alt='Small battery' width="60%">
</p>

### 4. (Optional) Add epoxy or hot glue to secure the battery leads

The battery leads are pretty fragile, so using something like epoxy to secure the leads isn't a bad idea. You may not be able to reconfigure the module if you do this, though, since it may be impossible to remove the battery without removing other components.

## Attaching a large battery

### 1. Pre-solder the battery pads on the module

It's very important to apply as little heat to the battery as possible to avoid causing a fire or making the battery explode.

To start, pre-solder the battery pads on the module with a generous amount of solder.

<p align="center">
    <img src='{{ "/assets/img/modules/battery/Large01.jpg"  |  relative_url }}' alt='Large battery' width="60%">
</p>

### 2. Solder the leads using a soldering iron

Make sure the + and - pads on the module are lined up with the positive and negative leads on the battery.

You'll want to touch the battery leads with the soldering iron for as little time as possible.

Keep the leads towards the edge of the board so that there's enough space to bend it over the board. Additionally, check the alignment of the battery so that it doesn't cover up the power header on the top side when you fold it over.

For the large battery, you'll want to make sure some solder is on top of the leads as well.

<p align="center">
    <img src='{{ "/assets/img/modules/battery/Large02.jpg"  |  relative_url }}' alt='Large battery' width="60%">
</p>
<p align="center">
    <img src='{{ "/assets/img/modules/battery/Large03.jpg"  |  relative_url }}' alt='Large battery' width="60%">
</p>

### 3. Carefully bend the battery over the top of the board

You don't want to break the leads, so be careful with this step!

<p align="center">
    <img src='{{ "/assets/img/modules/battery/Large04.jpg"  |  relative_url }}' alt='Large battery' width="60%">
</p>

### 4. (Optional) Add epoxy or hot glue to secure the battery leads

The battery leads are pretty fragile, so using something like epoxy to secure the leads isn't a bad idea. You may not be able to reconfigure the module if you do this, though, since it may be impossible to remove the battery without removing other components.