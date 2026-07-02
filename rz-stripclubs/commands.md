# rz-stripclubs — Commands & controls

---

## Admin commands

| Command | Config key | Permission | Description |
| --- | --- | --- | --- |
| `/creator:stripclub` | `Config.CreatorCommand` | `rz.stripclubs.admin`, `group.admin`, or command ace | Open the stripclub creator |
| `/admin:stripclub` | `Config.AdminCommand` | Same as above | Open the admin analytics panel |

Grant access in `server.cfg`:

```cfg
add_ace group.admin rz.stripclubs.admin allow
```

---

## In-game controls — pole & throwing

| Key | Action |
| --- | --- |
| **E** | Open dance menu (near pole, on duty) |
| **X** / **Backspace** | Stop throwing or stop pole dancing |

Customers use **target interactions** at throw targets to start tipping.

---

## In-game controls — lap dance

| Key | Action |
| --- | --- |
| **Q** | Exit lap dance |
| **E** | Tip during lap dance |
| **→** | Cycle camera angle |

Unlock lap dances by tipping a standalone dancer until their threshold is met, then use the target option **"Ask for a lap dance"**.

---

## Debug commands

Only available when `Config.Debug = true`:

| Command | Description |
| --- | --- |
| `/rzrebuildblips` | Rebuild club map blips |
| `/rzdebugdancers` | Debug standalone dancer state |
| `/rzlapdance_heading` | Tune lap-dance seat heading (dev) |
| `/rzlapdance_z` | Tune lap-dance seat Z offset (dev) |

Disable `Config.Debug` on production servers.

---

## Player flow summary

**Employee (dancer)**

1. Go on duty with the club job
2. Approach pole → **E** → select dance
3. Watch thrower leaderboard on HUD while performing
4. **X** to stop

**Customer**

1. Use throw target → pick cash tier or item
2. Stay in range or throwing stops automatically
3. For lap dances: tip until unlocked → target → **E** to tip in scene

**Admin**

1. `/creator:stripclub` — build or edit venues
2. `/admin:stripclub` — view analytics (requires SQL)
