# rz-stripclubs — Installation

---

## Requirements

| Dependency | Required |
| --- | :---: |
| oxmysql | Yes |
| MariaDB / MySQL | Yes |
| ox_lib | Recommended |
| Framework | Configurable |

---

## Steps

### 1. Create the RZ folder

```
resources/[rz]/rz-stripclubs/
```

### 2. Verify the built UI

Confirm `web/dist/` (or the build path listed in `fxmanifest.lua`) exists inside the resource.

{% hint style="danger" %}
If the download is missing the built UI, **do not** try to build on your live server — open a support ticket for a corrected package.
{% endhint %}

### 3. Run SQL

Execute **`sql/install.sql`** once against your server database.

Creates admin and analytics tables used by the strip club management system.

### 4. Configure `config.lua`

At minimum, review:

```lua
Config.Framework = 'auto'
Config.Target = 'auto'
Config.Inventory = 'auto'
Config.Notify = 'auto'
Config.Shop = 'auto'
Config.Banking = 'auto'
```

Match these to your server stack, or leave as `auto` if you're on a supported setup.

### 5. Start in server.cfg

After oxmysql, ox_lib, and your framework:

```cfg
ensure [rz]
```

Or individually:

```cfg
ensure rz-stripclubs
```

### 6. Verify

Check server console for startup errors, then visit a configured club location in-game.

---

## Custom integrations

If your inventory, banking, or notify system isn't supported out of the box, open a ticket in Discord with your stack details — custom adapters can be added to `server/custom/` and `client/custom/`.
