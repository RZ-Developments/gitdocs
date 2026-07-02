# rz-sound — Overview

**Version 0.9.0** · `[RZ] SOUND SCRIPT`

rz-sound is RZ Development's 3D positional audio engine for FiveM. It replaces or augments xsound with SyncGroups, vehicle occlusion, MLO door awareness, and streaming support for YouTube, SoundCloud, and Spotify URLs.

---

## Highlights

* **xsound-compatible** — `provide "xsound"`; existing scripts can call xsound exports
* **interact-sound compatible** — `provide "interact-sound"` for legacy sound triggers
* **SyncGroups** — attach audio to entities; multi-client drift correction
* **Vehicle occlusion** — doors, windows, sealed cabin muffling via raycasts
* **MLO doors** — skip interior muffling when configured doors are open (`/mlodoors` editor)
* **Zone sync** — walk out of range → mute (not pause); walk back → resync playhead
* **Dynamic volume** — optional tie to GTA SFX profile slider
* **Streaming** — YouTube, SoundCloud, Spotify URL playback with server-side search

---

## Used by

* **rz-carplay** — vehicle-attached 3D radio audio
* **rz-djbooth** — booth speaker SyncGroups (when `Config.PreferRzSoundSyncGroup = true`)

---

## Next steps

* [Installation](installation.md)
* [Configuration](configuration.md)
* [Commands](commands.md)
