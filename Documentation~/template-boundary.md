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
- one generic multi-package composition sample

The suite sample proves that the installed packages compose. It remains primitive,
generic, and isolated under `Samples~`; it is not a starter game or source of
product balance.

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

The template depends on `com.deucarian.auto-defense-suite` for installation and
also declares packages referenced directly by its own assemblies.

## Composition Sample

`Auto-Defense-Suite/Samples~/BasicAutoDefense` owns the full-stack composition
example, including persistence, progression, run upgrades, and idle rewards.

`Auto-Defense/Samples~/LeanAutoDefense` demonstrates only the focused framework
and its declared dependencies. The template remains the owner of playable product
content, prefabs, setup flow, and stronger authoring guidance.

## Future Work

Possible future packages, only if repeated use justifies them:

- `com.deucarian.auto-defense.persistence-integration`
- `com.deucarian.auto-defense.progression-integration`
- `com.deucarian.auto-defense.run-upgrades-integration`
- `com.deucarian.auto-defense.idle-progression-integration`
- `com.deucarian.auto-defense.ui-integration`

Do not add these integrations to the suite until their APIs are proven reusable outside one template.
