# rz-carplay — Overview

**Version 0.9.0** · `[RZ] CARPLAY SCRIPT`

rz-carplay brings a floating tablet-style CarPlay UI to any vehicle — stream from YouTube or Spotify, manage playlists, share queues with passengers, and hear music in true 3D through **rz-sound**.

---

## Highlights

* **Floating tablet UI** — dark glass visionOS-style overlay with sidebar apps
* **YouTube & Spotify** — paste URLs, search, queue tracks
* **Playlists** — liked songs, custom playlists, share codes, co-listen with nearby players
* **3D vehicle audio** — audio attached to the car via rz-sound SyncGroups
* **Passenger overlay** — compact now-playing bar for passengers (`/player`)
* **Streamer mode** — local mute for content creators
* **Framework adapters** — Qbox, QB, ESX, or standalone

---

## UI apps

| App | Purpose |
| --- | --- |
| **Library** | Liked songs and saved tracks |
| **Playlists** | Create, import Spotify playlists, share with others |
| **Queue** | Up next — reorder and skip |
| **Settings** | Passenger control, streamer mode, overlay preferences |
| **Dashboard** | Now playing with audio visualizer |

---

## Requirements

* **oxmysql** + MariaDB/MySQL
* **rz-sound** (required dependency)
* Framework optional (`Config.Framework = 'auto'`)

---

## Next steps

* [Installation](installation.md)
* [Configuration](configuration.md)
* [Commands & keybinds](commands.md)
