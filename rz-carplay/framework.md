# rz-carplay — Framework setup

rz-carplay resolves **player identifiers** and **display names** for playlists, liked songs, and sharing. Everything framework-specific lives in escrow-open custom files.

---

## Config

```lua
Config.Framework = 'auto'
```

| Value | When to use |
| --- | --- |
| `auto` | Recommended — detects Qbox → QB → ESX → standalone |
| `standalone` | No framework; uses license identifier |
| `qbox` | Force Qbox / qbx_core |
| `qbcore` | Force QB-Core |
| `esx` | Force ES Extended |

---

## File locations

```
rz-carplay/
└── server/
    └── custom/
        └── framework/
            ├── standalone.lua
            ├── qbox.lua
            ├── qbcore.lua
            └── esx.lua
```

Each file registers an adapter via `RegisterServerAdapter('framework', { ... })`.

---

## Custom framework

1. Copy `standalone.lua` to a new file (e.g. `custom.lua`)
2. Change `id` and `priority`
3. Implement:

```lua
GetPlayerIdentifier = function(source)
    -- return unique persistent id for this player
end,

GetPlayerDisplayName = function(source)
    -- return "First Last" or fallback
end,
```

4. Set `Config.Framework = 'your_id'` or raise `priority` above other adapters for `auto` detection

---

## What uses the framework

| Feature | Uses identifier |
| --- | :---: |
| Playlists & liked songs | Yes |
| Share codes | Yes |
| Co-listen nearby list | Yes (display name) |
| YouTube playback | No |
| Vehicle audio | No |

---

## Troubleshooting

**Playlists reset or show wrong owner**

* Confirm `Config.Framework` matches your server
* Check console for `[rz-carplay] framework adapter: ...` on resource start
* Verify `exports.qbx_core:GetPlayer(source)` (or equivalent) returns valid data

**Switching frameworks mid-wipe**

Player IDs change between standalone (license) and framework (citizenid). Existing playlist rows won't match new identifiers — expected after a framework migration.
