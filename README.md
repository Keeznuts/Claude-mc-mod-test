# Realistic Destruction (Fabric, Minecraft 1.21.1)

## Features
- **Structural collapse** – break the block holding something up and the unsupported part falls,
  bottom layer first. Anything connected to natural ground (stone, dirt, sand, bedrock) is safe,
  so terrain and caves behave normally; only structures that lose their connection fall.
- **Explosion debris** – TNT/creepers fling a share of destroyed blocks outward. Debris hurts
  entities and shatters on landing.
- Chests, furnaces and other block-entities stay put. Trees are ignored by default.

## Build
Requires JDK 21 and Gradle 8.8+.

    gradle build

The jar appears in `build/libs/realdestruction-1.0.0.jar`. Drop it in `mods/` together with
Fabric Loader 0.16+ and Fabric API for 1.21.1.

(No wrapper jar is included. Run `gradle wrapper` once if you want `./gradlew`.)

## Config
`config/realdestruction.json` is created on first launch:

| key | meaning |
|---|---|
| structuralCollapse | enable collapse on block break / explosion |
| explosionDebris | enable flying debris |
| treesFall | logs count as structure |
| maxComponentSize | masses bigger than this count as grounded |
| collapsePerTick | min blocks that start falling per tick |
| debrisChance | chance a destroyed block becomes debris |
| maxDebrisPerExplosion | cap per explosion |
| budgetMs | max ms/tick spent on support checks |

## Build without installing anything (GitHub Actions)
1. Create a free GitHub repo and upload everything in this folder (including the hidden `.github` folder).
2. Open the repo's **Actions** tab and wait for the `build` run to finish (a few minutes).
3. Open the run and download the `realdestruction-jar` artifact. Unzip it and use the jar that
   does NOT end in `-sources.jar`.
