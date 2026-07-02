# Support & updates

---

## Discord

For installation help, bug reports, and custom integration requests, join the RZ Development Discord (link on your Tebex purchase page or Keymaster receipt).

When opening a ticket, include:

* Script name and version (from `fxmanifest.lua`)
* Framework and inventory stack
* Server console error (full line, not a screenshot crop)
* Steps to reproduce

---

## Updates

1. **Back up** escrow-open files before updating:
   * `config.lua`
   * `server/custom/` and `client/custom/`
   * `db/booths.json` (rz-djbooth)
   * `data/mlo_doors.json` (rz-sound)
2. Download the new version from Tebex / Keymaster
3. Replace the resource folder **except** your backed-up configs
4. Re-apply config changes and restart

{% hint style="warning" %}
Never overwrite `config.lua` or booth JSON without backing up first.
{% endhint %}

---

## Custom integrations

We support custom framework, target, inventory, notify, and banking adapters on request. Provide:

* Resource names and export examples from your stack
* What behavior you need (e.g. "use ox_inventory for shop purchases")

Most integrations are added to `server/custom/` and `client/custom/` without modifying escrowed core files.

---

## Documentation

This site syncs from the **GitDocs** repository. If something is outdated, report it in Discord and we'll push an update.

**Live docs:** [rz-development.gitbook.io/docs](https://rz-development.gitbook.io/docs)

---

## Tebex product links

Link each product's **Documentation** field to the relevant section:

| Product | Suggested path |
| --- | --- |
| rz-sound | `/rz-sound/overview` |
| rz-carplay | `/rz-carplay/overview` |
| rz-djbooth | `/rz-djbooth/overview` |
| rz-stripclubs | `/rz-stripclubs/overview` |
