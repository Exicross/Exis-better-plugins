# BetterMap

BetterMap adds activity entrances to the standard area map. Hover over a badge to see the NPC and coordinates.

- **Island Sanctuary** at Baldin in Lower La Noscea (X: 24.9, Y: 34.8).
- **The Diadem** at Aurvael in the Firmament (X: 10.8, Y: 14.0).
- **Eureka Orthos shortcut** at Burnel in Mor Dhona (X: 21.8, Y: 8.1).
- **Ocean Fishing** at Dryskthota in Limsa Lominsa Lower Decks (X: 3.0, Y: 12.7). The fish badge sits beside the boarding point to leave room for the native `!`. It turns green during registration. Hover to see the Indigo and Ruby destinations for the current registration window or the next departure. [Lodestone Ocean Fishing notes](https://na.finalfantasyxiv.com/lodestone/topics/detail/cd927661a344f9996c8adf16fbb412570d4b7cab) · [Schedule rotation](https://github.com/FF14guide/eorzean-fish-guide)

Hover over a blue A Realm Reborn quest marker to see what the quest unlocks or which questline it continues. The hint appears above the quest title. Direct duty unlocks include the duty type, such as **Unlock: Halatali (Dungeon)**. Levequest unlocks are excluded.

## Install in Dalamud

1. In `/xlsettings`, open **Experimental → Custom Plugin Repositories**.
2. Add `https://raw.githubusercontent.com/Exicross/Exis-better-plugins/main/repo.json`, click **+**, and save.
3. Open `/xlplugins`, search for **BetterMap**, and click **Install**.

BetterMap requires Dalamud API 15. To remove it, open BetterMap in `/xlplugins` and click **Uninstall**. If it fails to load, check `%APPDATA%/XIVLauncher/dalamud.log`.

The map's marker toggle controls BetterMap badges. Holding Ctrl temporarily hides the badges so you can select the aetheryte.

## Settings

Open BetterMap's settings using its gear button in `/xlplugins`. **Hide entrances to locked activities** is off by default and saves immediately when changed. The filter uses the character's unlock quests. Diadem also requires a level 10 gatherer. Island Sanctuary counts either visiting access or access to your own island. [Lodestone Island Sanctuary access requirements](https://eu.finalfantasyxiv.com/lodestone/playguide/contentsguide/island_sanctuary/)

**Hide quest unlock hints** hides BetterMap's extra line in quest tooltips. It is off by default and saves immediately.

**Show Aether Current markers** shows field currents and quest reward locations from the installed game data. Hover a quest reward marker for the quest name and the zone it counts toward. The setting is on by default and saves immediately.

## Build

Use .NET 10 and a local Dalamud API 15 installation. The Dalamud SDK defaults to the XIVLauncher development library directory. To build against the installed release on Windows, set the path explicitly.

```powershell
dotnet build -c Release "-p:DalamudLibPath=$env:APPDATA/XIVLauncher/addon/Hooks/15.0.4.1/"
```

The Dalamud packager also writes `bin/Release/BetterMap/latest.zip`.

For local development, add the built `BetterMap.dll` under `/xlsettings → Experimental → Dev Plugin Locations`, then enable BetterMap under **Dev Tools** in `/xlplugins`.

## Release 0.2.7

- First distribution through Exis Better Plugins.
- Includes activity entrance markers, Ocean Fishing registration and route information, ARR quest unlock hints, and field and quest Aether Current markers.

BetterMap uses the Dalamud plugin framework and game data exposed by Lumina. Codex prepared the release and OpenAI ImageGen created the catalogue icon.
