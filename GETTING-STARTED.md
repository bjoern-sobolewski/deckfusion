# Unified Controls for Stream Deck

Native Windows x64 controls in one process: audio, application mixer, monitor
brightness and focus mode, Home Assistant, TeamSpeak, timers and system tools.

## Install

1. Install Elgato Stream Deck 6.5 or newer on Windows 10/11 x64.
2. Download the `.streamDeckPlugin` file from the
   [latest release](https://github.com/bjoern-sobolewski/streamdeck-releases/releases/latest).
3. Double-click the file and accept Stream Deck's plugin installation prompt.
4. Drag actions from **Unified Controls** onto your keys, then select your own
   audio devices, monitors, apps and automation entities in their settings.

No Rust, Python, Node, sccache or separate Visual C++ runtime installation is
needed. The installer adds this plugin alongside your existing plugins.
The optional bundled Mixer profile is for Stream Deck XL; individual actions
work on other models. Encoder support is implemented but not physically tested.

## Home Assistant

Add a Home Assistant action. Enter your instance URL and a dedicated long-lived
access token created in Home Assistant under your profile's Security settings.
Press **Save connection**. Tokens stay in Windows Credential Manager for your
Windows account; configure each computer separately. Use a trusted network for
HTTP or use HTTPS. Search entities by name, ID, area or device, filter domains
and save favorites. Light controls include brightness, supported colors,
temperature, effects and transitions; switches support on/off/toggle.

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
