# rz-djbooth — Framework setup

Same adapter pattern as rz-carplay — player identifiers power song request attribution and access checks.

---

## Config

```lua
Config.Framework = "auto"
```

Supported values: `auto`, `standalone`, `esx`, `qbcore`, `qbox`

---

## File locations

```
rz-djbooth/
└── server/
    └── custom/
        └── framework/
            ├── standalone.lua
            ├── qbox.lua
            ├── qbcore.lua
            └── esx.lua
```

Client-side custom adapters (target, notify, etc.) live in:

```
client/custom/
```

---

## Custom framework

Copy `standalone.lua`, set a unique `id`, implement `GetPlayerIdentifier` and `GetPlayerDisplayName`, then set `Config.Framework` to your adapter id.

For job/gang-based booth access, extend server custom adapters — open a support ticket if you need a template for your framework.

---

## Target adapters

`Config.Target = "auto"` selects:

1. ox_target (if started)
2. qb-target (if started)
3. standalone drawtext fallback

Force a specific target in config or add a custom client adapter under `client/custom/`.
