# rz-djbooth — Booth creator

The booth creator is an in-game tool for placing and editing DJ booth definitions without touching JSON by hand.

---

## Opening the creator

```
/creator:djbooth
```

Requires permission if `Config.UseAceForCreator = true`.

---

## What you define

Each booth saved to `db/booths.json` includes:

| Property | Purpose |
| --- | --- |
| **Booth ID** | Unique identifier used internally |
| **Interaction point** | Where the operator opens the control panel |
| **Speakers** | 3D audio emitters — each gets a SyncGroup |
| **Audio zone** | Area where listeners hear music and can request songs |
| **Default volume** | Starting speaker volume |

---

## Typical workflow

1. Run `/creator:djbooth` at your venue
2. Create a new booth or select an existing one
3. Place the **interaction** point where the DJ stands
4. Add **speaker** positions around the stage or room
5. Draw the **audio zone** (radius or box) covering the dance floor
6. Save — writes to `db/booths.json` immediately
7. Restart not required; booth syncs to connected clients

---

## Multi-speaker sync

Each speaker registers as an rz-sound SyncGroup (when `Config.PreferRzSoundSyncGroup = true`). All speakers play the same track in sync — useful for large venues with multiple prop speakers.

Group IDs follow the pattern `rzdj_{boothId}_{speakerId}`.

---

## Editing & removal

Re-open the creator, select the booth, and adjust positions or delete the booth entry. Always **back up `db/booths.json`** before bulk edits.

---

## Tips

* Set hear distance via the audio zone — defaults to `Config.DefaultHearDistance` for radius zones
* For MLO clubs, combine with rz-sound MLO door config so audio behaves correctly through open doors
* Test as two clients — one operator, one listener inside the zone

---

## Troubleshooting

**No audio at speakers**

* Confirm xsound or rz-sound is running
* Check `Config.PreferRzSoundSyncGroup` matches your audio resource
* Verify speaker coords aren't underground or inside collision

**Listeners can't request songs**

* Confirm they're inside the audio zone (not just near the DJ point)
* Check request limits in config — player may be on cooldown

**Booths gone after update**

* Restore `db/booths.json` from backup — it's not in escrow and can be overwritten by empty defaults if missing from the package
