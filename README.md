# RarityCraft — Minecraft 1.21.4 / Fabric

This is the **starter source project** for the mod concept. It is not yet a finished feature-complete mod or a compiled `.jar`.

## Requirements
- Minecraft Java Edition 1.21.4
- Java 21 JDK
- Fabric Loader and Fabric API for 1.21.4
- Gradle (the Gradle wrapper can be generated with `gradle wrapper`)

## Build
1. Install Java 21.
2. Open a terminal in this project folder.
3. Run `gradle wrapper` once if the wrapper files are not present.
4. Run `./gradlew build` (Windows: `gradlew.bat build`).
5. The mod jar, if compilation succeeds, will be in `build/libs/`.

The first build downloads Minecraft and Fabric dependencies, so internet access is needed.

## Current contents
- Fabric/Loom project scaffold for Minecraft 1.21.4 and Java 21.
- Rarity enum with the agreed weighted chances: Common 45%, Uncommon 25%, Rare 15%, Epic 8%, Legendary 5%, Mythic 1.5%, Divine 0.5%.
- Config file creation scaffold.

## Not implemented yet
This scaffold does **not** yet apply rarity to crafting outputs, implement item tooltips, add block/furnace rarity persistence, modify smelting yields, or implement armour powers/invisibility. Those features require version-specific mixins and client/server logic and should be implemented and tested in stages rather than misrepresented as already working.

## Planned implementation order
1. Attach persistent rarity data to crafted item stacks and show coloured rarity tooltips.
2. Ensure each crafted stack is rolled once (no preview rerolls or shift-click exploits).
3. Save rarity on placed crafting tables/furnaces and preserve it when broken/replaced.
4. Add furnace speed and bonus output for eligible ore recipes; handle stack limits safely.
5. Add four armour-slot abilities, including crouch-triggered Mythic Chestplate Shadow Cloak.
6. Add material-specific abilities, config options, particles, and multiplayer tests.

## Cloud build using GitHub Actions (no JDK install on your PC)
1. Create a new **private** repository on GitHub.
2. Upload the contents of this project folder (the files inside it, not the ZIP itself) to the repository.
3. Open the repository's **Actions** tab and enable Actions if GitHub asks.
4. Select **Build RarityCraft** and click **Run workflow**.
5. When the run finishes successfully, open the run and download the `raritycraft-build` artifact.
6. The artifact contains the built JAR. Put the appropriate mod JAR in the `mods` folder of your CurseForge Fabric 1.21.4 profile.

**Important:** GitHub Actions builds the current source scaffold only. A successful build does **not** mean the planned gameplay features have been implemented; see the "Not implemented yet" section above.
