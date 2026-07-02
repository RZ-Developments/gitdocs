# rz-carplay — Commands & keybinds

| Command | Keybind | Description |
| --- | --- | --- |
| `/carplay` | Bindable in FiveM settings | Open CarPlay UI — **must be seated in a vehicle** |
| `/player` | Bindable in FiveM settings | Open passenger now-playing overlay / edit mode |
| `rzcarplay_close` | **Escape** | Close CarPlay UI or exit overlay edit mode |

---

## `/carplay`

Opens the full tablet UI. Only works when the player is in a vehicle seat.

Bind a key in **Settings → Key Bindings → FiveM** — search for "Open CarPlay".

---

## `/player`

Opens the compact passenger overlay showing what's playing in the current vehicle.

In edit mode you can:

* Drag the overlay to a new screen position
* Open overlay settings (visibility, drag toggle)
* Press **Escape** to save position and exit edit mode

---

## Escape behavior

When the overlay settings drawer is open, **Escape** closes the drawer first. Press again to exit edit mode entirely.

---

## Streamer mode

Toggle from **Settings** inside the CarPlay UI. Mutes streamed audio locally — same concept as rz-sound's `/streamermode`.

---

## Playlist sharing

Sharing is done through the **Playlists** app in the UI — generate a share code and send it to another player. They import it from the Playlists app.

Co-listen (nearby sync) uses `Config.HearDistance` — players within range can follow the queue.
