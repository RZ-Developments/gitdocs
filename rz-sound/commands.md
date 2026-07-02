# rz-sound — Commands

| Command | Default key | Description |
| --- | --- | --- |
| `/soundvolume` | — | Open master volume menu (if enabled) |
| `/streamermode` | — | Toggle local mute for all streamed music |
| `/mlodoors` | — | MLO door editor for occlusion bypass (admin) |
| `/rzsoundstresstest` | — | Dev stress test — disable on production |

---

## Streamer mode

`/streamermode` mutes streamed audio **only for the player who runs it**. Useful for Twitch/YouTube creators avoiding DMCA strikes.

Players see a chat message confirming streamer mode on/off (configurable in `Config.Messages`).

---

## Volume menu

When `Config.VolumeMenu.enabled = true`:

* Adjust master volume with a slider
* Optionally sync volume to GTA's in-game music/SFX profile setting

---

## MLO doors editor

`/mlodoors` opens an in-game menu to register door props that bypass interior occlusion when open.

* Requires ace permission on the configured command (inherits `command` ace by default)
* Saves to `data/mlo_doors.json`
* Used by rz-djbooth venues (e.g. Vanilla Unicorn) when doors are configured
