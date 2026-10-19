# DeckFusion for Stream Deck

Native Windows x64 controls in one process: audio, application mixer, monitor
brightness and focus mode, Home Assistant, TeamSpeak, timers and system tools.

## Install

1. Install Elgato Stream Deck 6.5 or newer on Windows 10/11 x64.
2. Download the `.streamDeckPlugin` file from the
   [latest release](https://github.com/bjoern-sobolewski/deckfusion/releases/latest).
3. Double-click the file and accept Stream Deck's plugin installation prompt.
4. Drag actions from **DeckFusion** onto your keys, then select your own
   audio devices, monitors, apps and automation entities in their settings.

No Rust, Python, Node, sccache or separate Visual C++ runtime installation is
needed. The installer adds this plugin alongside your existing plugins.
The bundled Mixer and LightMenu profiles are for Stream Deck XL; individual actions
work on other models. Encoder support is implemented but not physically tested.

## Home Assistant

Add a Home Assistant action. Before setup, **Setup required** opens the connection
fields automatically. Enter your instance URL and a dedicated long-lived
access token created in Home Assistant under your profile's Security settings.
Press **Save and connect**; no restart is required. Tokens stay in Windows Credential Manager for your
Windows account; configure each computer separately. Use a trusted network for
HTTP or use HTTPS. Search entities by name, ID, area or device, filter domains
and save favorites. Light controls include brightness, supported colors,
temperature, effects and transitions; switches support on/off/toggle.

Choose **Key mode → Compact sensor card** to show up to six readings on one
key. Add rows, type an entity name, ID, room or device and choose an autocomplete
suggestion (or enter an entity ID directly). Choose an icon (or **None**), optional attribute,
room/group heading, unit override, and decimal places. Optional warning thresholds
color that row amber. Cards update from Home Assistant state events; missing
readings show a dash, and a disconnected card shows **HA offline**. Pressing a
sensor card does not run a service. All row controls are also available through
**Expand ↗** in the browser editor.

For easier-to-read labels, choose **Row labels → Large, beside value**. Short
labels work best beside icons and numbers. Leave **Card heading** empty to give
the readings more vertical space.

On Stream Deck XL, hold a key configured for one light or light group for 700 ms,
then release to open its light options menu. A short press toggles the light.
The menu offers supported brightness, white/color controls, matching scenes and
group members; Back returns to the previous profile. Explicit hold settings
override this automatic behavior.

Expand **Home Assistant connection** in an action's settings to see connection
status, retry timing and recent failures. Use **Reconnect now** to retry immediately,
**Refresh status** for a current snapshot, or **Copy diagnostics** when troubleshooting.
Saved connections recover automatically after startup, network, authentication
and state-subscription failures. Service commands are never replayed on reconnect.

## Clocks

Clock keys show digital time with a separate weekday and optional date row.
Choose local time or an IANA timezone and a 12/24-hour format. Press the clock
to show or hide seconds. Without seconds, it refreshes at minute boundaries.

## PC statistics

On a **System · CPU usage** key, choose **Display → CPU, free RAM, GPU, free VRAM**
for four compact icon rows. RAM and VRAM show free memory in binary GB/MB;
CPU and GPU show usage percentages. Readings refresh every second by default.
GPU readings use the installed NVIDIA driver, selecting the dedicated GPU with
the most VRAM. Unsupported readings show a dash. No monitoring app is required.

## Monitors and audio

Refresh the hardware list and choose all monitors, selected monitors or individual
brightness targets. DDC/CI must be enabled on monitors that require it. Brightness
zero usually dims a display; standby is a separate hardware-dependent option.
Focus mode can dim, put other displays in standby, or temporarily disconnect
them while keeping the primary/chosen display. Press again to restore or use a
restore timer. A standby monitor may need its physical button to wake.

Audio device selections belong to this PC. Automatic reconnect supports Windows
hardware identity and an unambiguous model fallback. Application controls need
an active audio session. TeamSpeak requires the ClientQuery addon and its API key.

## Update and recovery

Download a newer installer from the same release page and install it over the
existing plugin. Keep your plugin installed so your action assignments remain.
Stable action identifiers preserve profiles; local configuration and credentials
live outside the plugin directory. There is no automatic update checker yet.
GitHub's **Watch → Custom → Releases** can notify you about new versions.

Keep an exported Stream Deck profile backup before upgrades. Older installers
remain on the Releases page. This initial release has been tested on Windows 11
with Stream Deck XL; clean installation and upgrade on a second PC are still
pending. Some Windows audio routing and virtual desktop APIs are build-sensitive;
USB/service changes can require extra Windows permissions. No long-duration soak
test has been completed.

Logs and local state: `%LOCALAPPDATA%\Bjoern\UnifiedStreamDeck`. Credentials:
Windows Credential Manager entries `Bjoern.UnifiedStreamDeck/*`. To revoke Home
Assistant access, delete its dedicated token in Home Assistant.
