# rz-djbooth — Installation

---

## Requirements

| Dependency | Required |
| --- | :---: |
| xsound | Yes (fxmanifest dependency) |
| rz-sound | Recommended |
| oxmysql | No |
| Framework | Optional |

---

## Steps

### 1. Install audio backend

**Option A — rz-sound (recommended)**

```cfg
ensure rz-sound
```

Set in `config.lua`:

```lua
Config.PreferRzSoundSyncGroup = true
```

**Option B — xsound only**

```cfg
ensure xsound
```

```lua
Config.PreferRzSoundSyncGroup = false
```

### 2. Add rz-djbooth

```
resources/[rz]/rz-djbooth/
```

Verify `web/build/` and `db/booths.json` exist.

### 3. Configure

Edit `config.lua` — at minimum confirm framework and target settings:

```lua
Config.Framework = "auto"
Config.Target = "auto"
```

See [Configuration](configuration.md).

### 4. Start the resource

```cfg
ensure rz-djbooth
```

### 5. Create your first booth

Use the booth creator — see [Booth creator](booth-creator.md).

### 6. Test

1. Walk to a booth interaction point
2. Open the operator panel
3. Paste a YouTube URL and hit **Play**
4. Enter the audio zone as another player — confirm you hear synced 3D audio

---

## Vanilla Unicorn / MLO venues

If static GTA emitters bleed through your booth audio, defaults already disable common Vanilla Unicorn emitters when a track is loaded. Adjust in config:

```lua
Config.SuppressStaticEmittersInBoothZone = true
Config.DisabledStaticEmittersInBoothZone = { ... }
```

For rz-sound occlusion through club doors, configure MLO doors via `/mlodoors` — see [rz-sound commands](../rz-sound/commands.md).
