# rz-carplay — Installation

---

## Requirements

| Dependency | Required |
| --- | :---: |
| oxmysql | Yes |
| MariaDB / MySQL | Yes |
| rz-sound | Yes |
| Framework | Optional |

---

## Steps

### 1. Install dependencies first

```cfg
ensure oxmysql
ensure rz-sound
```

### 2. Add rz-carplay

```
resources/[rz]/rz-carplay/
```

Verify `web/build/index.html` exists.

### 3. Run SQL

Execute **`sql/install.sql`** once against your server database.

Creates:

* `rz_carplay_playlists` — player playlists and liked songs
* `rz_carplay_track_cache` — Spotify → YouTube resolution cache

### 4. Configure

Edit `config.lua`:

```lua
Config.Framework = 'auto'   -- or standalone / esx / qbcore / qbox
Config.OpenCommand = 'carplay'
Config.HearDistance = 15.0
```

See [Configuration](configuration.md) for all options.

### 5. Start the resource

```cfg
ensure rz-carplay
```

Or via folder:

```cfg
ensure [rz]
```

### 6. Test in-game

1. Enter a vehicle as driver or passenger
2. Run `/carplay`
3. Paste a YouTube URL and play

{% hint style="info" %}
Passengers can use `/player` to open the now-playing overlay and reposition it on their screen.
{% endhint %}

---

## Framework files

If `auto` doesn't detect your framework, add or edit an adapter in:

```
server/custom/framework/
```

See [Framework setup](framework.md).
