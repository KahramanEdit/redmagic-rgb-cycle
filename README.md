RedMagic AW22XXX RGB Control Center

A comprehensive KernelSU-based RGB control center for RedMagic 11 Pro.
Manage Logo, shoulder trigger and cooling fan LEDs from a single hub; remap the GameSpace key and synchronize the liquid cooling pump with the LEDs.

Why This Module?

RedMagic hardware supports RGB effects, but the software is limited. This module directly accesses the AW22XXX LED driver to unlock the full potential of the hardware:

· 🎨 Synchronize three zones: Logo, trigger and fan LEDs cycle colors simultaneously.
· ⚡ Independent per-zone control: Separate color palette and effect mode for each zone.
· 🎮 Remap the GameSpace key: Configure the hardware switch to launch any app you choose.
· ❄️ Liquid cooling pump synchronization: The pump automatically runs when LEDs are on, and stops when fully off.
· 💾 Persistent settings: All configuration is stored under /data/adb/, preserved across reboots.

Features

· Synchronized RGB cycle – Smooth color transitions across all three zones.
· Independent zone settings:
  · Logo & Trigger: 8 standard colors
  · Fan: 8 standard + 8 extended colors (16 total)
· Rich effect modes:
  · Logo / Trigger: Static, Breathing, Blink, Rapid Blink
  · Fan: Static, Breathing, Blink, Rapid Blink, Continuous Burn
· GameSpace key remapping:
  · Detects the physical GameSpace switch
  · Closes GameSpace and launches the selected app
  · Target app can be entered manually via WebUI or selected from a list
· Liquid cooling pump control:
  · Pump turns on automatically when LEDs are active
  · Recovers together with the fan after temporary LED off events
  · Fully stops when all LEDs are off
· Music awareness – LEDs stay on during media playback
· Game LED detection – Returns to normal behavior when game-controlled shoulder LEDs are released
· Smart shutdown – LEDs turn off only when all three zones receive a shutdown signal
· Wakelock management – Wakelock is held only while LEDs are active
· Dynamic configuration – Settings are re-read every 3 seconds, no script restart required
· Performance optimization – Automatic fallback to secondary sysfs path, -10 process priority

New in v3.0 – Advanced Zone & Timeout Features

· 🌍 Language selection – English (default) and Turkish; translations managed via external language files
· ⚡ Per-zone speed control – Fully independent of colors and of other zones
· ⌨️ Decimal precision speed input – Values like 0.10, 0.15, 0.12, 0.25 are supported
· 🖱️ Drag-and-drop color reordering – Only the selected zone's color order changes
· 🎯 Zone-specific effect following – Detects the current system effect and blends it with the user's color sequence
· ⏱️ Mandatory effect timings (when effect following is active):
  · Breathing: 0.9 s
  · Continuous burn: 0.9 s
  · Blink: 0.3 s
  · Rapid blink: 0.1 s
  · Static lighting is exempt from these limits
· 🔋 Battery protection timeout – Stops the RGB cycle after 1 / 5 / 15 / 30 minutes when the screen is off and idle
· 🛡️ Master priority rule – If an active scenario (game, music, charging) requires LEDs on, they always stay on
· 💾 Profile management – Create, save, load and delete profiles for different use cases
· 📤 Export – Backup current settings to internal storage
· 📥 Import – Load configuration from the module's dedicated directory
· 🔒 Config safety & fallback – Invalid or out-of-range values are automatically adapted to the default schema
· 🔄 Instant save mechanism – Every change is written immediately and synchronously to all storage backends
· 🕒 3-second polling – Background service checks for config changes every 3 seconds and applies them instantly

Installation

1. Download the ZIP file.
2. Open the KernelSU app.
3. Go to the Modules tab.
4. Tap Install and select the ZIP file.
5. Reboot your device.
6. Open KernelSU → Modules → tap RedMagic RGB Control Center to open the WebUI.

WebUI Usage

The WebUI includes:

· Mode selector (Loop / Static)
· Speed slider (0.1 s – 6.0 s) with decimal input
· Live preview circles for each zone
· Zone tabs:
  · Effect mode dropdown
  · Active / disabled color chips
  · Smart shuffle, random shuffle, reset, save buttons
  · Static color selection
· GameSpace remapping section:
  · Manual entry of target app package name
  · Loading and searching installed apps list
  · Selected target saved to /data/adb/gamespace_target.txt

Screenshots

Main Interface (Dark Mode)

screenshots/Mainuidark.jpg

Main Interface (Light Mode) & Speed Control

screenshots/Mainuilight.jpg

GameSpace Key Assignment

screenshots/Mainui2.jpg

LED Color & Effect Options

screenshots/Mainui3.jpg

Timeout & Color Shuffle

screenshots/Mainui4.jpg

Profile Save & Import/Export

screenshots/Mainui5.jpg

Reset & Main Menu End

screenshots/Mainui6.jpg

Timeout Selection

screenshots/Timeoutselector.jpg

Lighting Effects

screenshots/Lightingeffects.jpg

RGB Settings

screenshots/Rgbsettings.jpg

RGB Settings - Fan

screenshots/Rgbsettingsfan.jpg

RGB Effect Selection - Fan

screenshots/Rgbeffectselection.jpg

Compatibility

IMPORTANT: This module has only been tested on RedMagic 11 Pro.

· It has not been tested on other RedMagic models or different brands.
· Hardware paths and LED drivers may vary across generations; compatibility is unknown.

Warning & Disclaimer

USE AT YOUR OWN RISK.

· This module directly interacts with low-level kernel sysfs nodes and hardware controllers.
· Installation and use may result in hardware damage, software corruption, system instability, or LED failure.
· The developer is not responsible for any damage.
· This project is intended for educational and research purposes only, not for malicious use.

Always take a backup before installing.
