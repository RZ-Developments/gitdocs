# rz-carplay — Configuration

All options are in `config.lua`.

---

## Framework

| Option | Default | Description |
| --- | --- | --- |
| `Config.Framework` | `'auto'` | `auto`, `standalone`, `esx`, `qbcore`, `qbox` |

Controls how player IDs and display names are resolved for playlists and sharing.

---

## Commands

| Option | Default | Description |
| --- | --- | --- |
| `Config.OpenCommand` | `'carplay'` | Open the main CarPlay UI (must be in a vehicle) |
| `Config.MiniPlayerCommand` | `'player'` | Passenger now-playing overlay + position editor |

---

## Audio

| Option | Default | Description |
| --- | --- | --- |
| `Config.DefaultVolume` | `50` | Starting volume (0–100) |
| `Config.HearDistance` | `15.0` | How far outside the vehicle radio is audible (meters) |

Audio is routed through **rz-sound** and attached to the vehicle entity.

---

## Search & queue

| Option | Default | Description |
| --- | --- | --- |
| `Config.MaxSearchResults` | `6` | Max YouTube search results shown |
| `Config.MaxSyncQueueTracks` | `40` | Max tracks synced to nearby players in co-listen |

---

## Spotify (optional)

For more reliable Spotify playlist and album imports:

```lua
Config.SpotifyClientId = 'your_client_id'
Config.SpotifyClientSecret = 'your_client_secret'
```

Without credentials, public embed pages are scraped server-side as a fallback.

Create credentials at the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard).

---

## In-game settings

These are stored per-player in the UI (Settings app), not in `config.lua`:

* Allow front passenger control
* Mini now-playing bar visibility
* Streamer mode
* Overlay drag and position reset
