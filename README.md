# Ellion's FDDA Helmet Off Consume

Add-on for FDDA Redone (FDDA Redone - lizzardman) for STALKER Anomaly / GAMMA.
https://www.moddb.com/addons/fdda-redone

## Features

### Helmet off consume
- Using an eatable item while wearing a helmet takes the helmet off, then eats the item. No more waiting for helmet to come off
before queuing the next item to consume in the inventory.
- Optional "Require modifier key": the helmet is only taken off while the modifier key (Shift, Ctrl or Alt) is held.
- Optional "Re-equip helmet after use": the helmet is put back on after the item is consumed. If disabled, the helmet stays off. I found
this to be useful when you want to consume multiple items in a row.
- Respects whitelisted helmets that don't require removal to consume (FDDA's `helm = false` rule in `animations_settings.ltx`). Headgear listed in FDDA's `headgear_item_use_whitelist.ltx` (light headgear such as bandanas, balaclavas, cloth masks and hardhats) stays on.
- A use that FDDA refuses is respected and does not take the helmet off.
- Works with FDDA's helmet hotkey: the removed helmet is registered with the hotkey so its toggle key can put it back on.

### Instant helmet unequip
- When the helmet is taken off from the inventory or with FDDA's helmet hotkey, it leaves the slot immediately, so it can be equipped again right away.
- This was done to allow multiple queued consumes after a helmet unequip in the inventory window.
- FDDA's unequip animation, fade and nightvision steps still play.
- Only applies while FDDA Redone headgear animations are enabled in its MCM.

## MCM options

Menu Name: Helmet Off Consume, Menu id: `ellions_hoc`. MCM is optional; without it the defaults below are used.

| Option | Default | Description |
|---|---|---|
| Enable | On | Take the helmet off when using an eatable item with a helmet on. |
| Require modifier key | On | Only take the helmet off while the modifier key is held. |
| Modifier key | Ctrl | Shift, Ctrl or Alt. Used when "Require modifier key" is on. |
| Re-equip helmet after use | Off | Put the helmet back on after the item is consumed. |
| Instant helmet unequip | On | Remove the helmet from its slot immediately when unequipped from the inventory or the hotkey. |

## Requirements

- STALKER Anomaly or GAMMA
- FDDA Redone (FDDA Redone - lizzardman)
- MCM (optional, for the options menu)

## Installation

Copy the mod folder into your mod directory (or install it with your mod manager) so that `gamedata` is merged into the game data folder.  

MO2: Must come after FDDA edone - lizzardman
Manual: Copied in after lizzardman

## Modding

The script resolves FDDA's headgear module in `on_game_start` and wraps `on_unequip`, `on_toggle_unequip` and `liz_fdda_redone_consumables.modifiedAOIBU`. The wrappers call the original functions when a feature does not apply.
