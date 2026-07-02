# rz-stripclubs — Features

High-level overview of rz-stripclubs gameplay and admin systems.

---

## Player experience

* **Club interactions** — target-based interactions at configured club locations
* **Dancer / worker gameplay** — job-integrated routines (framework-dependent)
* **Customer interactions** — tipping, private dances, and club services
* **Shop integration** — purchase items through your configured inventory/shop adapter

---

## Business & economy

* **Banking integration** — club earnings route through your configured banking adapter
* **Configurable pricing** — tune costs and payouts in `config.lua`
* **Analytics** — SQL-backed tracking for admin dashboards and reporting

---

## Admin & management

* **Admin tools** — manage club state, workers, and settings
* **Analytics tables** — installed via `sql/install.sql` for server-side reporting
* **Ace / job permissions** — restrict management commands to staff roles

---

## Technical integrations

| System | Config key | Notes |
| --- | --- | --- |
| Framework | `Config.Framework` | Player data, jobs, money |
| Target | `Config.Target` | ox_target, qb-target, drawtext |
| Inventory | `Config.Inventory` | Item grants and shop stock |
| Notify | `Config.Notify` | Player feedback toasts |
| Shop | `Config.Shop` | In-club purchases |
| Banking | `Config.Banking` | Business account deposits |

All support `auto` detection for common Qbox/QB/ESX + ox_* stacks.

---

## Configuration depth

rz-stripclubs is highly configurable — most gameplay tuning lives in `config.lua` and location-specific data files shipped with the resource.

For location setup, job names, and permission details specific to your package version, refer to the config comments in the resource or ask in support.

---

{% hint style="info" %}
Feature availability may vary by package version. Check your Tebex purchase page or Discord announcements for the latest changelog.
{% endhint %}
