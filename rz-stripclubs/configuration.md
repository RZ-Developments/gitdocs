# rz-stripclubs — Configuration

All player-facing options are in `config.lua` (escrow-open).

---

## General

| Option | Default | Description |
| --- | --- | --- |
| `Config.Debug` | `true` | Extra console output; enables dev commands |
| `Config.CreatorCommand` | `"creator:stripclub"` | Open the in-game creator |
| `Config.AdminCommand` | `"admin:stripclub"` | Open the admin analytics panel |
| `Config.AdminFlushSeconds` | `15` | How often analytics events flush to MySQL |
| `Config.CreatorItemsMax` | `1500` | Max inventory items sent to creator NUI (prevents CEF overload) |

---

## Integrations

| Option | Default | Description |
| --- | --- | --- |
| `Config.Framework` | `"auto"` | `auto`, `esx`, `qbcore`, `qbox`, `mythic`, `standalone` |
| `Config.Target` | `"auto"` | `auto`, `ox_target`, `qb-target`, `standalone_drawtext` |
| `Config.Inventory` | `"auto"` | `auto`, `ox_inventory`, `qs-inventory`, `standalone` |
| `Config.Shop` | `"standalone"` | `standalone` (NUI) or `inventory` (ox_inventory) |
| `Config.Notify` | `"auto"` | `auto`, `ox_lib` |
| `Config.Banking` | `"auto"` | Auto-detect or force a banking adapter |

### Banking adapters (auto-detected)

| Resource | Adapter file |
| --- | --- |
| qb-banking | `server/custom/banking/qb-banking.lua` |
| qb-management | `server/custom/banking/qb-management.lua` |
| Renewed-Banking | `server/custom/banking/renewed-banking.lua` |
| kartik-banking | `server/custom/banking/kartik-banking.lua` |
| okokBanking | `server/custom/banking/okok-banking.lua` |
| ESX addon accounts | `server/custom/banking/esx-addonaccount.lua` |
| mythic-finance | `server/custom/banking/mythic.lua` |

If none are running, society payouts are skipped with a console warning.

---

## Economy

| Option | Default | Description |
| --- | --- | --- |
| `Config.ShopHouseCutPercent` | `0` | House cut on public shop sales (0–100) |
| `Config.SelfServeCreditsSociety` | `true` | Employee wholesale shop purchases credit society when true |

Per-location and per-pole/per-dancer splits are set in the **creator**, not in `config.lua`:

* `percentageSociety`, `percentageDancer`, `percentageThrower`
* `giveMoneyBack` — return a portion to the thrower
* `maxThrowers` — cap simultaneous throwers at a pole/dancer

---

## NPC schedules

| Option | Default | Description |
| --- | --- | --- |
| `Config.NpcDancerTimeSource` | `"server"` | `"server"` = real server hour · `"game"` = in-game clock from the throwing player's client |

NPC on-duty windows are configured per pole in the creator (multiple windows per day supported).

---

## Custom adapters

When `auto` doesn't match your stack, edit files in:

```
server/custom/   — framework, banking, inventory, notify, callback
client/custom/   — framework, target, inventory, notify, callback
```

These folders are escrow-open — safe to edit on your server.

---

## Locales

UI strings live in `locales/*.json` (escrow-open). Default is `locales/en.json`. Uses ox_lib locale system (`ox_lib 'locale'` in fxmanifest).

---

## Location data

Club definitions are **not** in `config.lua` — they're in `db/`:

```
db/manifest.json
db/location_1.json
db/location_2.json
...
```

Back up `db/` before updates. Each server typically has its own club layout.
