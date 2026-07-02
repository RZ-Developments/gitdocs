# rz-stripclubs — Creator workflow

The creator is a raycast-based NUI editor. Everything you place saves to `db/` and syncs to connected players without a server restart.

---

## Opening the creator

```
/creator:stripclub
```

Requires `rz.stripclubs.admin` ace (or `group.admin`).

---

## Step-by-step

### 1. Create a location

Set the basics for a new club:

* **Blip** — map icon and label
* **Job name** — which job counts as club staff
* **Throw interval** — cooldown between throws
* **Default economy splits** — society / dancer / thrower percentages for the whole location

### 2. Place poles

* Raycast to position each pole
* Add **throw targets** around the pole or bar area
* Configure **throw items** — cash tiers (min/max) or inventory items
* Optional overrides: society %, dancer %, thrower %, max throwers, give-money-back

### 3. NPC pole (optional)

On a pole's NPC tab:

* Enable NPC dancer
* Set ped model and purchase price
* Pick pole animation
* Add **on-duty schedule windows** (multiple per day)
* Uses `Config.NpcDancerTimeSource` for time calculation

Customers purchase the NPC at the pole, then throw during scheduled hours.

### 4. Standalone dancers

Separate from poles — stage or private areas:

* Ped model and idle dance animation
* Throw targets and throw items
* **Lap-dance seats** — use the seat picker in the creator
* **Unlock threshold** — total tips before lap dance is offered
* **Two-girl partner** — optional second dancer for duo scenes
* Bouncer eject ties to bouncer spawn points

### 5. Shops

* Place shop interaction zones
* Add items and prices
* Enable **self-serve wholesale** for on-duty employees
* If `Config.Shop = "inventory"`, shops register with ox_inventory instead of the built-in NUI

### 6. Bouncers

* Place bouncer spawn points near lap-dance areas
* Bouncers handle ejects when customers run out of tip money

### 7. Save

Save the location — writes `db/location_<id>.json` and updates `db/manifest.json`. All clients receive the updated club data immediately.

---

## Economy overrides

Location defaults apply everywhere unless overridden:

| Field | Purpose |
| --- | --- |
| `percentageSociety` | % to club/society account |
| `percentageDancer` | % to the dancing player |
| `percentageThrower` | % returned to tipper (if `giveMoneyBack`) |
| `maxThrowers` | Max simultaneous throwers at this pole/dancer |
| `giveMoneyBack` | Whether throwers get a cut back |

Override at **location**, **pole**, or **standalone dancer** level in the creator UI.

---

## Tips

* Set lap-dance **unlock threshold** low on test dancers while building
* Configure at least one NPC schedule window that includes your testing hour
* Back up `db/` before major edits or resource updates
* Use `Config.CreatorItemsMax` if your inventory is huge and the creator NUI slows down
* For Mythic servers, map banking in `server/custom/banking/mythic.lua` before testing society payouts

---

## Migrating old data

If you have a legacy `clubLocations.json`, the resource auto-migrates on first start to the `db/` format. Check `clubLocations.json.bak` and verify all locations appear in the creator before deleting backups.

See the resource's `db/README.md` for migration details.
