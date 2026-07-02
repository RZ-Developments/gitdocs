# rz-stripclubs — Features

---

## Creator UI

Open with `/creator:stripclub` (admin only).

Raycast-based editor — no map restarts:

* Create and edit club **locations** (blip, job, default economy splits)
* Place **poles** with throw targets and throw items (cash tiers or inventory items)
* Configure **NPC pole dancers** — model, purchase price, multi-window shift schedules
* Add **standalone dancers** — idle animations, throw targets, lap-dance seats, unlock threshold, two-girl partner
* Place **shops** (bar POS) and **bouncer** spawn points
* Override economy per pole or dancer (society %, dancer %, thrower %, max throwers, give-money-back)

All saves write to `db/` and sync live.

---

## Pole dancing (employees)

1. Employee goes on duty with the club job
2. Approach a pole, press **`E`** → pick a pole dance animation
3. Synced pole scene plays
4. Customers use throw targets to tip cash or items
5. Dancer HUD shows **live top tippers** and thrower count
6. Press **`X`** or **Backspace** to stop dancing

Throwing auto-stops when the customer walks out of range.

---

## Throwing & tipping

* Cash tiers or inventory items configured per throw target
* Splits route to **society**, **dancer**, and optionally back to **thrower** (`giveMoneyBack`)
* **Max throwers** cap per pole/dancer — prevents overcrowding
* Per-location defaults with per-pole/per-dancer overrides

---

## NPC pole dancers

* Customers purchase the NPC slot at the pole (if enabled and priced)
* NPC loops a configured pole animation during **on-duty windows**
* Multiple schedule windows per day (e.g. 14:00–18:00 and 21:00–02:00)
* Schedule time source: real server hour or in-game clock (`Config.NpcDancerTimeSource`)
* Outside schedule hours, throw targets are unavailable

---

## Lap dances

Standalone dancers support full lap-dance scenes:

1. Customer tips until the **unlock threshold** is met
2. Target option changes to **"Ask for a lap dance"**
3. Scene plays at configured seat positions
4. **`E`** — tip during the dance
5. **`→`** — cycle cinematic cameras
6. **`Q`** — exit
7. Run out of money → **bouncer ejects** the customer (ragdoll shove)
8. Optional **two-girl mode** when a partner dancer is configured

---

## Shops

Two modes via `Config.Shop`:

| Mode | Behavior |
| --- | --- |
| `standalone` | Built-in NUI checkout at shop zones |
| `inventory` | Registers ox_inventory shops |

Features:

* Public pricing with optional **house cut** (`Config.ShopHouseCutPercent`)
* **Employee self-serve** wholesale pricing at the same shop
* When `Config.SelfServeCreditsSociety = true`, employee wholesale purchases credit the society account

---

## Bouncers

Spawn points placed in the creator. Used for lap-dance ejects when a customer can't pay or misbehaves.

---

## Admin panel

Open with `/admin:stripclub`. Requires `sql/install.sql`.

Tracks:

* Throws and tip values (society / dancer / thrower breakdown)
* Lap dance starts, ends, and in-scene tips
* Shop sales
* Dancer presence events

Dashboard includes:

* Revenue KPI cards with period-over-period deltas
* Trend charts
* Club comparison table
* Live activity feed

Filter by **24h / 7d / 30d / all time** and by club scope.

Events flush to MySQL every `Config.AdminFlushSeconds` (default 15s).

---

## Integrations

Auto-detection or force via `config.lua`. Custom adapters in `server/custom/` and `client/custom/` (escrow-open).

| System | Config key | Supported by default |
| --- | --- | --- |
| Framework | `Config.Framework` | auto, esx, qbcore, qbox, mythic, standalone |
| Target | `Config.Target` | auto, ox_target, qb-target, standalone_drawtext |
| Inventory | `Config.Inventory` | auto, ox_inventory, qs-inventory, standalone |
| Shop | `Config.Shop` | standalone, inventory |
| Notify | `Config.Notify` | auto, ox_lib |
| Banking | `Config.Banking` | auto — qb-banking, qb-management, renewed-banking, kartik-banking, okokBanking, esx_addonaccount, mythic-finance |

If no banking script is detected, society payouts are dropped and a warning prints to the server console on first throw.

For **Mythic Finance**, edit `server/custom/banking/mythic.lua` to map job names to organization account IDs.
