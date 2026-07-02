# rz-djbooth — Configuration

All options are in `config.lua`.

---

## General

| Option | Default | Description |
| --- | --- | --- |
| `Config.Debug` | `true` | Print debug lines to server console |
| `Config.Framework` | `"auto"` | Player identity adapter |
| `Config.Target` | `"auto"` | Interaction system |
| `Config.InteractionRadius` | `1.5` | Booth target sphere radius (m) |

---

## Audio

| Option | Default | Description |
| --- | --- | --- |
| `Config.PreferRzSoundSyncGroup` | `true` | Use rz-sound SyncGroups when available |
| `Config.DefaultHearDistance` | `45.0` | Default hear distance for radius-type audio zones |
| `Config.SuppressGameRadioInBoothZone` | `true` | Mute GTA radio inside active booth zones |
| `Config.SuppressStaticEmittersInBoothZone` | `true` | Mute configured static emitters (e.g. Vanilla Unicorn) |
| `Config.DisabledStaticEmittersInBoothZone` | `{ ... }` | Emitter names to suppress |

---

## Creator access

| Option | Default | Description |
| --- | --- | --- |
| `Config.CreatorCommand` | `"creator:djbooth"` | Open booth creator |
| `Config.CreatorAce` | `"creator.djbooth"` | Ace permission for creator |
| `Config.UseAceForCreator` | `false` | Require ace instead of open access |
| `Config.BoothDataFile` | `"db/booths.json"` | Where booth definitions are saved |

---

## Listener settings

| Option | Default | Description |
| --- | --- | --- |
| `Config.ListenerSettingsCommand` | `"djsettings"` | Reposition listener now-playing overlay |

---

## Song requests

| Option | Default | Description |
| --- | --- | --- |
| `Config.MaxPendingRequests` | `20` | Max pending requests per booth |
| `Config.MaxRequestsPerPlayer` | `3` | Max active requests per player |
| `Config.RequestCooldownSec` | `30` | Cooldown between requests (seconds) |

---

## Booth data file

`db/booths.json` is **escrow-open** — back it up before updates. Contains booth IDs, speaker positions, audio zones, and interaction points created via the booth creator.
