# rz-stripclubs — Overview

**Version 2.1.0** · `[RZ] STRIPCLUB SCRIPT`

A full strip-club economy for FiveM — in-game creator, pole dancing, cash/item throwing, NPC dancers with schedules, lap dances, shops, bouncers, and a MySQL-backed admin analytics panel. Built on **ox_lib** with adapters for ESX, QBCore, Qbox, Mythic, and standalone.

---

## Highlights

| Area | What it does |
| --- | --- |
| **Creator UI** | Place clubs, poles, throw targets, standalone dancers, shops, bouncers, and blips with a raycast NUI editor |
| **Pole dancing** | Job-gated synced pole scenes with a live thrower leaderboard on the dancer HUD |
| **Throwing** | Tip poles or standalone dancers with cash or inventory items — configurable society / dancer / thrower splits |
| **NPC pole dancers** | Purchasable NPCs with custom model, dance, and multi-window on-duty schedules |
| **Lap dances** | Unlock via tipping threshold; per-touch tips, camera cycling, solo or two-girl mode, bouncer eject |
| **Shops** | Standalone NUI checkout or ox_inventory shop registration; optional employee self-serve wholesale |
| **Admin panel** | Revenue KPIs, trends, club comparison, and live activity feed (MySQL-backed) |
| **Economy overrides** | Per-pole and per-dancer society/dancer/thrower splits and max thrower caps |

---

## Requirements

* **ox_lib** (required dependency)
* **oxmysql** + MariaDB/MySQL (admin analytics)
* Supported **framework** — ESX, QBCore, Qbox, Mythic, or standalone
* **Target** — ox_target, qb-target, or drawtext fallback
* **Banking** script for society payouts (optional — warns in console if missing)

---

## Data storage

Club locations are saved under **`db/`**:

* `manifest.json` — list of location IDs
* `location_<id>.json` — one file per club

No restart needed after saving from the creator — data syncs live to all clients.

---

## Next steps

* [Installation](installation.md)
* [Features](features.md)
* [Configuration](configuration.md)
* [Commands & controls](commands.md)
* [Creator workflow](creator.md)
