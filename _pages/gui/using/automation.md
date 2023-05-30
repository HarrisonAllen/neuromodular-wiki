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

# Automation Sequence Introduction
Automation sequences allow for automated control of modules based on various triggers. For example, you could perform the following sequence using automations:
1. Trigger: Serial message "TTL Pulse 1" received
2. Action: Start stimulation on Module 3.P Pin 1 (Blue LED)
3. Action: Wait 5 seconds
4. Action: Stop stimulation on Module 3.P Pin 1 (Blue LED)
5. Repeat

Here is an example of a simple automation sequence to show how it looks when a sequence is running:
1. Trigger: Manual
2. Action: Wait 250 ms
3. Action: Wait 500 ms
4. Action: Wait 750 ms
5. Repeat/Don't repeat (depending on repeat setting)

<p align="center">
    <img src='{{ "/assets/img/gui/using/sequence/Sequence Loop Example.png" | relative_url }}' alt='Example of automation sequence' width="80%">
</p>