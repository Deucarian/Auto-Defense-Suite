# Template Boundary

Use this rule:

```text
Suite = install the toolset
Template = playable starter game
```

## Suite

`com.deucarian.auto-defense-suite` owns:

- package dependency stack
- install guidance
- dependency documentation
- suite/template boundary documentation
- import and dependency-resolution validation notes

The suite does not create gameplay content.

## Future Template

`com.deucarian.template.game.idle-auto-defense` should own:

- scenes
- prefabs
- placeholder art and audio
- example balance
- example enemies, weapons, modules, spawn channels, and objectives
- example run upgrade setup
- example save/progression/offline glue
- starter UI when that phase is reached
- setup wizard
- "make your own game from this" guide

The template should depend on `com.deucarian.auto-defense-suite` instead of duplicating the full dependency list.

## Current Auto Defense Sample

`Auto-Defense/Samples~/BasicAutoDefense` remains a package-contained sample. It can inform the future template, but it should not be moved into the suite.

The sample should remain small, primitive, and useful for proving package composition. The template can grow into a playable starter game with scenes, prefabs, setup flow, and stronger authoring guidance.

## Future Work

Possible future packages, only if repeated use justifies them:

- `com.deucarian.auto-defense.persistence-integration`
- `com.deucarian.auto-defense.progression-integration`
- `com.deucarian.auto-defense.run-upgrades-integration`
- `com.deucarian.auto-defense.idle-progression-integration`
- `com.deucarian.auto-defense.ui-integration`

Do not add these integrations to the suite until their APIs are proven reusable outside one template.
