# RZ Development

**Original FiveM scripts and custom tooling — built for performance, designed for simplicity.**

Welcome to the official documentation for [RZ Development](https://rz-development.gitbook.io/docs). Here you'll find install guides, configuration references, and feature overviews for every released script.

---

## Scripts

| Script | Description |
| --- | --- |
| [**rz-sound**](rz-sound/overview.md) | 3D positional audio engine — xsound & interact-sound compatible, vehicle occlusion, SyncGroups |
| [**rz-carplay**](rz-carplay/overview.md) | In-vehicle CarPlay UI — YouTube/Spotify streaming, playlists, passenger overlay |
| [**rz-djbooth**](rz-djbooth/overview.md) | In-world DJ booths — operator panel, song requests, booth creator, synced 3D audio |
| [**rz-stripclubs**](rz-stripclubs/overview.md) | In-game creator, pole dancing, lap dances, NPC schedules, shops, admin analytics (v2.1) |

---

## Quick start

1. Read [Dependencies & frameworks](getting-started/dependencies.md) to confirm your stack.
2. Install [**rz-sound**](rz-sound/installation.md) first — carplay and djbooth depend on it.
3. Follow each script's installation page in order.
4. Adjust `config.lua` for your server and restart.

{% hint style="info" %}
**New here?** Start with the [Getting started overview](getting-started/overview.md) for a full walkthrough.
{% endhint %}

---

## Recommended start order

```
oxmysql  →  rz-sound  →  rz-carplay / rz-djbooth / rz-stripclubs
```

---

## Support

Need help or a custom integration? See [Support & updates](support/support.md).
