# rz-sound — Configuration

All options live in `config.lua`. Only the most commonly changed settings are listed here — open the file for the full list.

---

## General

| Option | Default | Description |
| --- | --- | --- |
| `Config.Debug` | `false` | Verbose client/server logging |
| `Config.RefreshTime` | `100` | How often listener position updates (ms) |
| `Config.distanceBeforeUpdatingPos` | `40` | Start position updates within this range (m) |
| `Config.DistanceAlgorithm` | `"exponential"` | Volume falloff: `linear`, `exponential`, `square` |

---

## Volume menu

| Option | Default | Description |
| --- | --- | --- |
| `Config.VolumeMenu.enabled` | `true` | Enable `/soundvolume` menu |
| `Config.VolumeMenu.command` | `"soundvolume"` | Chat command |
| `Config.VolumeMenu.defaultMaster` | `1.0` | Default master volume (0–1) |
| `Config.VolumeMenu.defaultSyncGame` | `false` | Follow in-game music SFX slider |

---

## Occlusion

| Option | Default | Description |
| --- | --- | --- |
| `Config.Occlusion.enabled` | `true` | Raycast-based muffling |
| `Config.Occlusion.vehicleSealedGain` | `0.20` | Volume when listener is outside sealed vehicle |
| `Config.Occlusion.vehicleOpenGain` | `0.95` | Volume when vehicle door is open |
| `Config.Occlusion.AdvancedMLODoors` | `true` | Respect configured MLO doors |
| `Config.Occlusion.MLODoorsMenu.command` | `"mlodoors"` | In-game door editor command |

---

## Streaming & search

| Option | Default | Description |
| --- | --- | --- |
| `Config.Streaming.youtube` | `true` | Allow YouTube URLs |
| `Config.Streaming.soundcloud` | `true` | Allow SoundCloud URLs |
| `Config.Streaming.spotify` | `true` | Allow Spotify URLs |
| `Config.Search.youtubeApiKey` | `""` | YouTube Data API key for in-game search |

---

## Performance

When many sounds are active, rz-sound scales down update rates automatically.

| Option | Default | Description |
| --- | --- | --- |
| `Config.Performance.heavySoundThreshold` | `20` | Active sounds before heavy mode |
| `Config.Performance.proximityBatch` | `true` | Batch proximity updates to NUI |

---

## Static ambient sounds

Server-spawned ambient loops — disabled by default:

```lua
Config.StaticSounds = {
    enabled = false,
    sounds = {},
}
```

See `server/static_sounds.lua` (escrow-open) for format.

---

## interact-sound emulator

| Option | Default | Description |
| --- | --- | --- |
| `Config.interact_sound_enable` | `true` | Emulate interact-sound exports |
| `Config.interact_sound_file` | `"ogg"` | Default file extension |

Sound files go in `html/sounds/*.ogg` and `*.mp3`.
