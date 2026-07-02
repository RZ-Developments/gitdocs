# rz-sound — Installation

---

## Requirements

* FiveM server (Cerulean, Lua 5.4)
* No database required
* No framework required

---

## Steps

### 1. Install the resource

```
resources/[rz]/rz-sound/
```

Confirm `web/build/` exists inside the resource folder.

### 2. Start in server.cfg

```cfg
ensure rz-sound
```

Place **before** any resource that depends on it (e.g. rz-carplay).

### 3. Configure (optional)

Edit `config.lua` — defaults work for most servers. See [Configuration](configuration.md).

### 4. Test

In-game, run `/soundvolume` to open the master volume menu (if enabled).

Use `/streamermode` to toggle muting all streamed music locally.

---

## Migrating from xsound

rz-sound **provides** xsound. Scripts that `ensure xsound` can use rz-sound instead:

```cfg
ensure rz-sound
# ensure xsound   ← not needed
ensure rz-carplay
```

Most xsound export calls are shimmed automatically. Edge-case exports are listed in the escrow-open shim files.

---

## MLO door editor

If you use interior occlusion near club doors or venue entrances:

1. Set `Config.Occlusion.AdvancedMLODoors = true`
2. In-game, run `/mlodoors` (requires admin ace on `command`)
3. Doors save to `data/mlo_doors.json`
