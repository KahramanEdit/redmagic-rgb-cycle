# RedMagic AW22XXX RGB Color Cycle & KSU Web UI Control

## Description
This KernelSU (KSU) module enables dynamic, continuous RGB color cycling for RedMagic devices utilizing the AW22XXX LED controller. It seamlessly synchronizes the device's logo, shoulder triggers, and cooling fan LED rings through an established color sequence. 

The module features a built-in KernelSU Web UI, allowing users to dynamically adjust the speed of the color transitions in real-time, ranging from 0.3 seconds to 6.0 seconds. The selected speed is saved persistently and survives device reboots.

## Features
*   **Synchronized Cycling:** Cycles lighting across all supported LED zones (Logo, Triggers, Fan).
*   **Accurate Color Palette:** Uses a verified sequence of 8 distinct hardware-level hex codes (Red, Pink, Orange, Yellow, Green, Cyan, Blue, Purple).
*   **Dynamic Speed Control:** Integrated KSU Web UI slider for instant transition speed adjustments.
*   **Persistent Settings:** Your preferred speed setting is saved directly to root memory (`/data/adb/`) and remains active after restarting the device.

## Prerequisites
*   A rooted RedMagic device.
*   **KernelSU (KSU)** installed and functional (Magisk can be used for the core script, but the Web UI control specifically requires KernelSU).
*   The device hardware must utilize the `aw22xxx_led` I2C controller path (`/sys/devices/platform/soc/.../leds/aw22xxx_led/effect`).

## Installation Instructions
1.  Download the provided `.zip` module file.
2.  Open the **KernelSU** manager application.
3.  Navigate to the **Modules** tab.
4.  Tap **Install** and select the downloaded `.zip` file.
5.  Wait for the flashing process to complete.
6.  **Reboot** the device.
7.  After rebooting, open the KernelSU app, navigate to Modules, and tap on this module's name to access the Web UI speed slider.

## Compatibility & Testing
**IMPORTANT:** This module has been developed and strictly tested **only on the RedMagic 11 Pro**. 
*   It has **not** been tested on other RedMagic models or different smartphone brands.
*   The hardware paths and LED controllers may differ across device generations; therefore, compatibility with other models is entirely unknown. 

## Disclaimer & Warning
**USE AT YOUR OWN RISK.**
*   This module interacts directly with low-level kernel sysfs nodes and hardware controllers. 
*   By installing this module, you acknowledge that you take full responsibility for any potential consequences.
*   The creator assumes **no liability** for any hardware damage, software bricking, system instability, LED component failure, or any other technical malfunction that may occur.
*   This project was created purely for **educational and research purposes** to understand I2C controller behavior. It is not intended for malicious use.
*   
