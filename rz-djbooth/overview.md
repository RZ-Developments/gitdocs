# rz-djbooth — Overview

**Version 0.9.0** · `[RZ] DJBOOTH SCRIPT`

rz-djbooth adds placeable in-world DJ booths with a full operator panel, listener song requests, and synced 3D audio across multiple speakers.

---

## Highlights

* **Operator panel** — play YouTube URLs, manage queue, pause/skip/stop, volume and timeline
* **Listener overlay** — compact now-playing card with request drawer
* **Song requests** — rate-limited queue with pending limits per player
* **Booth creator** — in-game tool to place booths, speakers, and audio zones
* **Synced 3D audio** — multi-speaker SyncGroups via rz-sound (recommended) or xsound
* **Game audio suppression** — mute GTA radio and Vanilla Unicorn static emitters in booth zones
* **Target integration** — ox_target, qb-target, or standalone drawtext

---

## Roles

| Role | Experience |
| --- | --- |
| **Operator / DJ** | Full booth control panel at the booth interaction point |
| **Listener** | Now-playing overlay when inside the audio zone; can request songs |
| **Admin / creator** | Booth creator command to add and edit booth definitions |

---

## Requirements

* **xsound** (listed dependency) or **rz-sound** with `Config.PreferRzSoundSyncGroup = true`
* No database — booth data saved to `db/booths.json`
* Framework optional

---

## Next steps

* [Installation](installation.md)
* [Configuration](configuration.md)
* [Booth creator](booth-creator.md)
