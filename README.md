Tabii, işte verdiğin formata sadık kalarak, resim yolları screenshots/ klasörüne göre düzenlenmiş İngilizce README:

---

RedMagic AW22XXX RGB Control Center

KernelSU-based RGB control center for RedMagic 11 Pro. Synchronizes logo, trigger and fan LEDs via AW22XXX LED driver; real-time management with WebUI.

Why This Module?

RedMagic hardware supports RGB effects, but the software is limited. This module directly accesses the AW22XXX LED driver to unlock the full potential of the hardware:

· 🎨 Synchronize three zones: Logo, trigger and fan LEDs cycle colors simultaneously.
· ⚡ Independent per-zone control: Separate color palette and effect mode for each zone.
· 🎮 Remap the GameSpace key: Configure the hardware switch to launch any app you choose.
· ❄️ Liquid cooling pump synchronization: The pump automatically runs when LEDs are on, and stops when fully off.
· 💾 Persistent settings: All configuration is stored under /data/adb/, preserved across reboots.

Features

Synchronized RGB Cycle

Smooth color transitions across all three zones.

screenshots/Mainuidark.jpg

Independent Zone Settings

· Logo & Trigger: 8 standard colors
· Fan: 8 standard + 8 extended colors (16 total)

screenshots/Rgbsettings.jpg
screenshots/Rgbsettingsfan.jpg

Rich Effect Modes

· Logo / Trigger: Static, Breathing, Blink, Rapid Blink
· Fan: Static, Breathing, Blink, Rapid Blink, Continuous Burn

screenshots/Lightingeffects.jpg
screenshots/Rgbeffectselection.jpg

GameSpace Key Remapping

Detects the physical GameSpace switch, closes GameSpace and launches the selected app. Target app can be entered manually or selected from a list.

screenshots/Mainui2.jpg

· Liquid Cooling Pump Control: Pump turns on automatically when LEDs are active, recovers after temporary off events, and fully stops when all LEDs are off.
· Music Awareness: LEDs stay on during media playback.
· Game LED Detection: Returns to normal behavior when game-controlled shoulder LEDs are released.
· Smart Shutdown: LEDs turn off only when all three zones receive a shutdown signal.
· Wakelock Management: Wakelock is held only while LEDs are active.
· Dynamic Configuration: Settings are re-read every 3 seconds, no script restart required.
· Performance Optimization: Automatic fallback to secondary sysfs path, -10 process priority.

New in v3.0 – Advanced Zone & Timeout Features

· 🌍 Language selection – English (default) and Turkish; translations managed via external language files
· ⚡ Per-zone speed control – Fully independent of colors and of other zones

screenshots/Mainuilight.jpg

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

screenshots/Timeoutselector.jpg

· 🛡️ Master priority rule – If an active scenario (game, music, charging) requires LEDs on, they always stay on
· 💾 Profile management – Create, save, load and delete profiles for different use cases

screenshots/Mainui5.jpg

· 📤 Export – Backup current settings to internal storage
· 📥 Import – Load configuration from the module's dedicated directory
· 🔒 Config safety & fallback – Invalid or out-of-range values are automatically adapted to the default schema
· 🔄 Instant save mechanism – Every change is written immediately and synchronously to all storage backends
· 🕒 3-second polling – Background service checks for config changes every 3 seconds and applies them instantly

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

screenshots/Mainui3.jpg

· GameSpace remapping section:
  · Manual entry of target app package name
  · Loading and searching installed apps list
  · Selected target saved to /data/adb/gamespace_target.txt

screenshots/Mainui4.jpg
screenshots/Mainui6.jpg

Installation

1. Download the ZIP file.
2. Open the KernelSU app.
3. Go to the Modules tab.
4. Tap Install and select the ZIP file.
5. Reboot your device.
6. Open KernelSU → Modules → tap RedMagic RGB Control Center to open the WebUI.

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

---

Bu düzenleme, verdiğin sıralamayı ve screenshots/ klasör yapısını korur. Resimlerin görünmemesi sorunu dosya adı büyüklük-küçüklük uyumu veya GitHub önbelleğinden kaynaklanıyorsa, bu haliyle çalışacaktır. İstersen ./ ekleyerek veya raw URL kullanarak daha da garantiye alabilirsin.
