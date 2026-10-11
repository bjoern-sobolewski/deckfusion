# DeckFusion for Stream Deck

Download the [latest Windows x64 installer](https://github.com/bjoern-sobolewski/deckfusion/releases/latest).

One native Rust process provides 46 actions for audio and application mixing,
monitor brightness and focus mode, Home Assistant, TeamSpeak, timers and system
controls. Configure your own devices and Home Assistant connection on each PC.

Version 0.1.3 improves Home Assistant recovery and connection diagnostics, adds
clearer action help, and fixes browser-editor saves, monitor selections and
encoder feedback. Light menus and digital clocks remain included.

## Install and update

Download the `.streamDeckPlugin` asset and double-click it. Requires Windows 10/11
x64 and Elgato Stream Deck 6.5+. No separate runtime or developer tools are needed.
Install newer packages over the existing plugin to preserve action assignments.
Use **Watch → Custom → Releases** for new-version notifications. Automatic
in-plugin update checking is not implemented.

Read [Getting Started](GETTING-STARTED.md) for connection setup, monitor behavior
and recovery. Release downloads include SHA-256 checksums; license texts are
bundled with the plugin. Never share your Home Assistant token or local state.

The first release is tested on Windows 11 with Stream Deck XL. Second-PC clean
installation/upgrade, physical encoders and long-duration soak testing remain
pending. Monitor standby/wake is hardware-dependent; some Windows audio/desktop
compatibility APIs may require maintenance after Windows updates.

This public repository contains release downloads and documentation. Development
source is maintained in a separate private repository. GitHub's automatically
generated source archives contain only this repository's documentation.
