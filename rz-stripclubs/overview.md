# rz-stripclubs — Overview

**[RZ] STRIPCLUB SCRIPT**

A full strip club experience for FiveM — player interactions, business management, and admin tooling with framework, inventory, target, and banking integrations.

---

## Integrations

Configured via `config.lua`:

| Adapter | Options |
| --- | --- |
| Framework | `auto`, ESX, QB-Core, Qbox, standalone |
| Target | ox_target, qb-target, standalone |
| Inventory | ox_inventory, qb-inventory, etc. |
| Notify | ox_lib, qb, esx, custom |
| Shop / banking | Server-specific adapters |

Set each to `auto` for automatic detection, or force a specific integration.

---

## Requirements

* **oxmysql** + MariaDB/MySQL
* **SQL install** — `sql/install.sql` (admin/analytics tables)
* Framework and addon resources matching your config

---

## Next steps

* [Installation](installation.md)
* [Features](features.md)
