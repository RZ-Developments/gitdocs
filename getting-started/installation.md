# Installation

Use this guide for **any** RZ script. Script-specific steps (SQL, extra deps) are linked at the bottom.

---

## 1. Create the RZ folder

In your server's `resources` directory, create a folder named `[rz]` (brackets included):

```
resources/[rz]/
```

---

## 2. Add the resource

Copy the resource folder into `resources/[rz]/`.

Example for rz-carplay:

```
resources/[rz]/rz-carplay/fxmanifest.lua
```

{% hint style="danger" %}
If a script ships a web UI, the folder must include **`web/build/`** (pre-built NUI). Escrow downloads from Tebex include this. If `web/build/` is missing, open a support ticket — do not run `npm install` on a live server unless you're developing.
{% endhint %}

---

## 3. Run SQL (if required)

Some scripts need database tables before first start.

| Script | SQL file |
| --- | --- |
| rz-carplay | `sql/install.sql` |
| rz-stripclubs | `sql/install.sql` (admin analytics — optional for gameplay) |
| rz-djbooth | None — booths saved to `db/booths.json` |
| rz-sound | None |

Run the `.sql` file **once** against your server database using HeidiSQL, DBeaver, or your host's SQL panel.

{% hint style="info" %}
We recommend **HeidiSQL** or your host's SQL tool for production. Avoid XAMPP/phpMyAdmin for live servers.
{% endhint %}

---

## 4. Configure `config.lua`

Each resource has a `config.lua` at its root. Open it and set:

* **Framework** — usually `auto` (recommended) or force `standalone`, `esx`, `qbcore`, `qbox`
* **Commands** — rename chat commands if they clash with other resources
* **Distances / limits** — tune for your server population and map

Defaults work on most Qbox/QB/ESX setups out of the box.

---

## 5. Start order in `server.cfg`

Add resources **after** oxmysql and your framework:

```cfg
ensure oxmysql
ensure qbx_core          # or qb-core / es_extended — your framework

ensure [rz]
```

Or start individually:

```cfg
ensure rz-sound
ensure rz-carplay
ensure rz-djbooth
```

{% hint style="warning" %}
**rz-sound must start before rz-carplay.** rz-carplay declares `rz-sound` as a dependency. rz-djbooth works with xsound or rz-sound — set `Config.PreferRzSoundSyncGroup = true` when using rz-sound.
{% endhint %}

---

## 6. Verify in-game

1. Restart the server (or `ensure` the resource).
2. Check the server console for `[rz-*]` startup messages or errors.
3. Test the script's main command (see each script's commands page).

---

## Script-specific guides

* [rz-sound installation](../rz-sound/installation.md)
* [rz-carplay installation](../rz-carplay/installation.md)
* [rz-djbooth installation](../rz-djbooth/installation.md)
* [rz-stripclubs installation](../rz-stripclubs/installation.md)
