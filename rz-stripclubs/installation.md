# rz-stripclubs — Installation

---

## Requirements

| Dependency | Required |
| --- | :---: |
| ox_lib | Yes |
| oxmysql | Yes (admin panel) |
| MariaDB / MySQL | Yes (admin panel) |
| Framework | Configurable |
| Banking | Optional (society payouts) |

---

## Steps

### 1. Add the resource

```
resources/[rz]/rz-stripclubs/
```

### 2. Build the UI

The NUI loads from **`web/dist/`**. If your Tebex download includes a pre-built UI, skip this step.

```bash
cd web
npm install
npm run build
```

Confirm these exist:

```
web/dist/index.html
web/dist/assets/
```

{% hint style="danger" %}
If `web/dist/` is missing from your purchase, open a support ticket — do not run npm on a live production server unless you know what you're doing.
{% endhint %}

### 3. Run SQL

Execute **`sql/install.sql`** once against your server database.

Creates `rz_stripclubs_events` — used by the admin analytics panel for throws, lap dances, shop sales, and dancer activity.

The script runs without SQL, but **`/admin:stripclub` will not work** until the table exists.

### 4. Configure `config.lua`

At minimum:

```lua
Config.Framework = "auto"
Config.Target = "auto"
Config.Shop = "standalone"   -- or "inventory" for ox_inventory shops
Config.Banking = "auto"
```

See [Configuration](configuration.md) for all options.

### 5. Grant admin ACE

Staff who use the creator or admin panel need permission:

```cfg
add_ace group.admin rz.stripclubs.admin allow
```

Also accepts `group.admin` or the configured command ace.

Per-player example:

```cfg
add_ace identifier.license:xxxxxxxx rz.stripclubs.admin allow
```

### 6. Start in server.cfg

After ox_lib and oxmysql:

```cfg
ensure ox_lib
ensure oxmysql
ensure rz-stripclubs
```

Or via folder:

```cfg
ensure [rz]
```

{% hint style="info" %}
This resource declares `dependency '/assetpacks'` — ensure CFX asset packs are available on your server host.
{% endhint %}

### 7. Create your first club

1. Join as an admin
2. Run `/creator:stripclub`
3. Create a location, place poles/dancers/shops, and save

See [Creator workflow](creator.md).

---

## Location data migration

If upgrading from an older version that used a single `clubLocations.json`:

On first start the resource auto-migrates to `db/manifest.json` + `db/location_<id>.json`, backs up the old file to `clubLocations.json.bak`, and marks migration complete.

Keep the `.bak` until you've verified all clubs loaded correctly.

---

## Escrow-open files

You can edit after purchase:

* `config.lua`
* `shared/npc_schedule.lua`
* `server/custom/**/*.lua`
* `client/custom/**/*.lua`
* `server/sv_open.lua`
* `locales/*.json`
* `db/*.json`
