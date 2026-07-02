# Overview

This section covers everything you need before installing any RZ script.

---

## What you'll need

| Requirement | Notes |
| --- | --- |
| **FiveM server** | Recent artifacts — Cerulean + Lua 5.4 (`fx_version 'cerulean'`, `lua54 'yes'`) |
| **MariaDB or MySQL 8.x** | Required for scripts that use SQL (e.g. rz-carplay) |
| **oxmysql** | Database connector — loaded via `@oxmysql/lib/MySQL.lua` |
| **Framework** (optional) | ESX, QB-Core, Qbox, or standalone — most scripts auto-detect |

{% hint style="warning" %}
Even if you run **MariaDB**, the FiveM resource is still named **oxmysql**. It speaks the MySQL protocol MariaDB provides.
{% endhint %}

---

## Folder layout

We recommend grouping RZ resources under a shared folder:

```
resources/
└── [rz]/
    ├── rz-sound/
    ├── rz-carplay/
    ├── rz-djbooth/
    └── rz-stripclubs/
```

Brackets included — `ensure [rz]` starts everything inside.

---

## Typical install flow

1. **Create** the `[rz]` folder in `resources/`.
2. **Drop** each purchased resource into `[rz]/`.
3. **Run SQL** where required (see each script's install page).
4. **Configure** `config.lua` for your framework and preferences.
5. **Add** to `server.cfg` after oxmysql and your framework:

```cfg
ensure oxmysql
ensure [rz]
```

---

## Next steps

* [Installation](installation.md) — step-by-step for any RZ script
* [Dependencies & frameworks](dependencies.md) — per-script requirements and adapter options
