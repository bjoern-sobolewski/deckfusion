# Changelog

## 0.1.1 — 2026-10-05

First portable Windows x64 release with 46 actions.

- One native Rust process for audio, monitors, Home Assistant, timers and system controls.
- Searchable Home Assistant entities with lights, colors, brightness and switches.
- All/selected/per-monitor brightness; focus, temporary disconnect and restore.
- Mixer paging and encoder controls, reconnect-aware audio device selection.
- Per-computer configuration and Windows Credential Manager token storage.
- Static Visual C++ runtime and automatic per-user notification identity registration.
- Installers and manual upgrades through the public GitHub Releases page.

Validated with Rust tests/clippy, native SDK-host smoke tests, live read-only Home
Assistant checks, inspector checks and official Elgato packaging validation.
Windows 11 / Stream Deck XL is the tested hardware. A second-PC clean install and
upgrade, physical encoder use and a long-duration soak remain pending.
