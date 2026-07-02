# rz-djbooth — Commands & keybinds

| Command | Keybind | Description |
| --- | --- | --- |
| `/creator:djbooth` | — | Open booth creator (configurable) |
| `/djsettings` | — | Edit listener now-playing overlay position |
| `rzdjbooth_close` | **Escape** | Close booth operator UI |

---

## Booth creator

Default command: **`/creator:djbooth`**

Configure in `config.lua`:

```lua
Config.CreatorCommand = "creator:djbooth"
Config.UseAceForCreator = false   -- set true + ace to restrict
Config.CreatorAce = "creator.djbooth"
```

When `UseAceForCreator = true`, grant ace to admins:

```cfg
add_ace group.admin creator.djbooth allow
```

See [Booth creator](booth-creator.md) for the full workflow.

---

## Listener overlay

**`/djsettings`** opens edit mode for the compact now-playing card listeners see inside the audio zone.

* Drag to reposition
* Access request and settings side tabs
* **Escape** closes the UI

---

## Operator panel

Opened via target interaction at the booth — no default chat command.

Side tabs on the operator panel:

| Tab | Purpose |
| --- | --- |
| **Settings** | Booth preferences |
| **Queue** | Upcoming tracks |
| **Requests** | Pending listener song requests |

---

## Escape

**Escape** closes the operator panel when focused. Same binding as other RZ NUI scripts.
