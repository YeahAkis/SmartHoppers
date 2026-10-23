# SmartHoppers

Choose what a hopper is allowed to take. Every hopper gets its own whitelist or blacklist, edited from a menu. SmartHoppers is a Paper plugin, players join with a vanilla client. Runs on Paper, Purpur and Folia from 1.21 up to 26.3.

## Using it

Right click a hopper with the Hopper Item (an iron shovel by default) to open its menu. If you turn the item off in the config, sneak and right click with an empty hand instead.

In the menu:

- The toggle on the left turns the filter on or off for that hopper.
- The wool switches between whitelist and blacklist.
- Click an item in your own inventory to add it to the filter.
- Click an entry in the filter to remove it.
- Right click an entry in the filter to turn exact match on or off for it.

An entry normally matches every item of its material. With exact match it only matches items that are identical, including name, lore, custom model data and head texture. That is what you want for things like player heads, where every head is the same material.

Hold shift while you click an item in your inventory to add it as an exact match straight away, without the extra right click afterwards.

Filters are saved in `plugins/SmartHoppers/hoppers.yml`, and a hopper's filter is deleted when the hopper is broken.

## The Hopper Item

It's craftable by default:

```
C G C
R S R
C G C
```

C is a copper ingot, G a gold ingot, R redstone and S an iron shovel. `/smarthoppers item` gives you one. Name, lore, material, custom model data and the recipe are all in `config.yml`, and the material can be a Nexo item (`nexo-<id>`).

## Commands and permissions

| Command | Permission | What it does |
| --- | --- | --- |
| `/smarthoppers item` (`/sh item`) | `smarthoppers.item` | Gives you the Hopper Item |
| `/smarthoppers reload` | `smarthoppers.reload` | Reloads the configs and the menu |
| (using the Hopper Item) | `smarthoppers.use` | Opening a hopper's menu, on by default |

## Config

- `config.yml`: the Hopper Item and its recipe, and whether Nexo is used for the menu.
- `gui.yml`: the menu title, slot layout, and the item used for each button. Materials can be Nexo items (`nexo-<id>`).

The menu respects land protection through [ProtectionLib](https://github.com/NexoMC/ProtectionLib), so players can only open hoppers they could normally use. That covers WorldGuard, Towny, HuskTowns, Lands, Factions, PlotSquared and CrashClaim.

## Building

```
gradle build
```

The jar ends up in `build/libs`. It needs JDK 21 or newer.

Publishing to Modrinth is `gradle modrinth`. It reads the token from the `modrinthToken` Gradle property (or `MODRINTH_TOKEN`) and uploads the shaded jar with the newest section of `CHANGELOG.md` as the changelog. Add `-PmodrinthDryRun` to see what would be sent without uploading.

## Metrics

SmartHoppers reports anonymous usage to [bStats](https://bstats.org/plugin/bukkit/SmartHoppers/25706). You can turn that off in `plugins/bStats/config.yml`.
