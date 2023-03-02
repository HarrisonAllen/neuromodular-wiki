---
layout: topic
title: Programming the Blue Board
permalink: /blue-board/programming/
previous: /blue-board/components/
base: /blue-board/
# next: 
---

Note: This guide is for Windows only

## Set up the SEGGER Embedded Studio environment

1. Download and install [SEGGER Embedded Studio for ARM V5.42 for Windows](https://www.segger.com/downloads/embedded-studio/Setup_EmbeddedStudio_ARM_v542_win_x64.exe)
    - Leave all of the settings default
    - Any time that you see this screen, just hit continue
    <p align="center">
    <img src='{{ "/assets/img/blue-board/programming/1-Continue.png" | relative_url }}' alt='Continue Screen'>
    </p>
2. Download and install the nRF5 SDK V15.2
    1. Go to the [download page](https://www.nordicsemi.com/Products/Development-software/nrf5-sdk/download)
    2. Scroll down and select `15.2.0 nRF5 SDK`
    <p align="center">
      <img src='{{ "/assets/img/blue-board/programming/2-Select.png" | relative_url }}' alt='Select 15.2.0 nRF5 SDK'>
    </p>
    3. Scroll down and unselect all of the options in `SoftDevices`
    <p align="center">
      <img src='{{ "/assets/img/blue-board/programming/3-Options.png" | relative_url }}' alt='Unselect all SoftDevice options'>
    </p>
    4. Scroll down and download the zip file
    <p align="center">
      <img src='{{ "/assets/img/blue-board/programming/4-Download.png" | relative_url }}' alt='Download the zip'>
    </p>
    5. Extract the sdk to your desired location
    - Note that you will have to do two extractions to get to the SDK folder
    - The resulting folder name should be `nRF5_SDK_15.2.0_9412b96`
3. Navigate to the following folder in the nRF5 SDK: `nRF5_SDK_15.2.0_9412b96\examples\ble_central`
4. Rename the folder `ble_app_uart_c` to `ble_app_uart_c-old` (keep the original folder in case you want to use it later)
5. Download [ble_app_uart_c.zip](https://github.com/HarrisonAllen/neuromodular-wiki/releases/download/v1.1.0/ble_app_uart_c.zip)
6. Extract the .zip file to `nRF5_SDK_15.2.0_9412b96\examples\ble_central`
7. Navigate to `nRF5_SDK_15.2.0_9412b96\examples\ble_central\ble_app_uart_c\pca10056\s140\ses`
8. Launch `ble_app_uart_c_pca10056_s140.emProject` (by double clicking)

Now that you've done this, launching segger should default to opening this project and `main.c`.

## Programming the blue board

1. Launch SEGGER Embedded Studio and open the project. If the project does not open automatically, folow steps 7-8 of the previous section to reopen the project.
2. [Plug the Blue Board into your computer]({{ "/blue-board/components/" | relative_url }})
    - A file explorer should pop up with a title of JLINK
    <p align="center">
      <img src='{{ "/assets/img/blue-board/programming/5-Popup.png" | relative_url }}' alt='JLINK in file explorer'>
    </p>
3. In SEGGER, go to the top left and select `Target`->`Connect J-Link`
    <p align="center">
      <img src='{{ "/assets/img/blue-board/programming/6-Connect.png" | relative_url }}' alt='Menu item for connecting'>
    </p>
    - If you are prompted with a firmware update, select `Yes`
    - You can check that the Blue Board is properly connected by clicking on `Target` in the top left. The menu should look like this:
    <p align="center">
      <img src='{{ "/assets/img/blue-board/programming/7-Connected.png" | relative_url }}' alt='Menu after successful connection'>
    </p>
4. Go to the top left and select `Build`->`Build and Run`
    <p align="center">
      <img src='{{ "/assets/img/blue-board/programming/8-Build.png" | relative_url }}' alt='Menu item for building and running the firmware'>
    </p>
    - The console at the bottom should show the following after a successful build:
    <p align="center">
      <img src='{{ "/assets/img/blue-board/programming/9-Success.png" | relative_url }}' alt='Console displaying a successful build'>
    </p>
5. The Blue Board is now ready to be used with the GUI!