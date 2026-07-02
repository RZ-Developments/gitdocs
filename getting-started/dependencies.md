# Dependencies & frameworks

RZ scripts are built to run **standalone where possible**, with optional framework adapters for player identity and display names.

---

## Shared dependencies

| Dependency | Used by | Purpose |
| --- | --- | --- |
| **oxmysql** | rz-carplay, rz-stripclubs | MySQL/MariaDB queries |
| **rz-sound** | rz-carplay (required) | 3D vehicle audio, SyncGroups |
| **xsound** or **rz-sound** | rz-djbooth | Booth speaker playback |

---

## Per-script matrix

| Script | oxmysql | rz-sound | xsound | SQL |
| --- | :---: | :---: | :---: | :---: |
| rz-sound | — | — | replaces via `provide` | No |
| rz-carplay | Yes | **Yes** | — | Yes |
| rz-djbooth | — | Optional* | Yes (listed dep) | No |
| rz-stripclubs | Yes | — | — | Yes |

\* Set `Config.PreferRzSoundSyncGroup = true` in rz-djbooth when rz-sound is installed — recommended for best sync and occlusion.

---

## Framework adapters

Scripts that need a player identifier (playlists, requests, etc.) support:

| Value | Behavior |
| --- | --- |
| `auto` | Picks the highest-priority adapter whose framework resource is running |
| `standalone` | License identifier — no framework required |
| `qbox` | Qbox / qbx_core — citizenid |
| `qbcore` | QB-Core — citizenid |
| `esx` | ES Extended — identifier |

Custom adapters live in **`server/custom/`** (escrow-open). Copy an existing adapter and edit exports to match your framework.

* [rz-carplay framework setup](../rz-carplay/framework.md)
* [rz-djbooth framework setup](../rz-djbooth/framework.md)

---

## Target systems (rz-djbooth)

| Value | Behavior |
| --- | --- |
| `auto` | ox_target → qb-target → drawtext fallback |
| `ox_target` | Force ox_target |
| `qb-target` | Force qb-target |
| `standalone_drawtext` | 3D text + key press |

---

## Inventory / notify / banking (rz-stripclubs)

rz-stripclubs supports multiple integrations via `config.lua`:

* `Config.Framework`, `Config.Target`, `Config.Inventory`, `Config.Notify`, `Config.Shop`, `Config.Banking`

Set each to `auto` or force a specific adapter. Custom integrations can be requested via support.

---

## Escrow-open files

Files you can edit after purchase (not encrypted):

| Script | Open files |
| --- | --- |
| rz-carplay | `config.lua`, `server/custom/**/*.lua` |
| rz-djbooth | `config.lua`, `db/booths.json`, `server/custom/**`, `client/custom/**` |
| rz-sound | `config.lua`, export shims, emulators, occlusion, MLO doors |
| rz-stripclubs | See Tebex package listing |
