# Changelog

## 0.1.6 — 2026-10-14

- Home Assistant keys now offer **Compact sensor card** mode with up to six
  independent entity or attribute readings. Configure searchable rows, card and
  room headings, optional labels, units, decimal places, and row order in the
  embedded inspector or expanded browser editor.
- Each row can show a vector icon or **None**, allowing ppm and temperature
  values to stand on their own. Values fit the available space; optional warning
  thresholds highlight individual readings in amber.
- Cards update from Home Assistant events, initialize from cached readings, and
  recover after reconnecting. Missing readings show a dash; disconnected cards
  show **HA offline**. Pressing a sensor card does not call a service.
- Verified with Rust and Python tests, inspector save checks, native card,
  light-menu and connection-recovery tests, and live read-only sensor readings.
  Local layout tools and personal configuration remain outside the installer.

## 0.1.5 — 2026-10-14

- Local deployment starts Stream Deck in the normal Windows user context,
  preventing packaged editors from giving it a private AppData view that differs
  from startup at sign-in. The temporary launcher task is removed after use.
- Home Assistant diagnostics show the actual backing settings path and flag
  redirected storage, making missing configuration after a restart diagnosable.

## 0.1.4 — 2026-10-11

- A new installation without Home Assistant settings or a token shows **Setup
  required** and opens the connection fields. Save and connect applies the setup
  immediately without restarting Stream Deck.
- Missing first-install data is separated from invalid JSON, unreadable settings,
  vault failures and loss of a previously complete configuration. Real failures
  retain automatic recovery and diagnostic history. Diagnostics include the
  exact settings file path used by the running plugin.

## 0.1.3 — 2026-10-11

- Home Assistant reconnects automatically after unavailable startup settings or
  credentials, dropped connections, authentication rejection, missed heartbeat
  replies and failed state subscriptions. Retry deadlines remain active under
  heavy event traffic; service commands are never replayed.
- Home Assistant settings show connection status, retry timing, recent failures
  and reconnect counts, with Reconnect now, Refresh status and Copy diagnostics.
  Connection history is bounded and excludes credentials.
- Clearer tooltips and descriptions explain all 46 actions. Settings use a compact
  layout, with a collapsed entity picker for configured Home Assistant keys.
- Browser-editor changes save in order, and closing the editor submits the final
  settings snapshot. Per-monitor brightness selections persist, and editing a
  dial preserves its encoder feedback channel.
- Local profile tools preserve configured native mixer slots and support updating
  a light overview without regenerating detail pages. These personal setup tools
  are excluded from the installer.

## 0.1.2 — 2026-10-05

- Hold a Home Assistant light or light-group key to open its on-device options
  menu, with brightness, white/color presets, scenes and individual lights.
  The reusable LightMenu profile is included for Stream Deck XL.
- Digital clocks show separate time, weekday and optional date rows. Press a
  clock key to toggle seconds; minute-only clocks refresh at minute boundaries.
- Faster light-menu navigation uses cached entity capabilities and state,
  batches watch updates and avoids redundant rendering and registry requests.
- Audio notifications wake the worker directly. Idle timers, monitor restoration
  and system workers wake when needed, reducing background polling.
- Light labels wrap within two lines, and clock/shutdown artwork is refreshed.
- Local configuration scripts back up and apply room layouts, clock settings
  and light labels; these personal setup tools are not included in the installer.

Validated with Rust tests, strict Clippy, Python migration tests, native SDK host
and editor checks, light-menu and performance regression tests, release privacy
checks and official Elgato packaging validation. Second-PC install/upgrade,
physical encoders and a long-duration soak remain pending.

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
