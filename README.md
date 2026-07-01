# Deucarian Auto Defense Suite

`com.deucarian.auto-defense-suite` is an install stack for Deucarian Auto Defense projects.

The suite exists for teams that already have a Unity project and want the full Auto Defense toolset installed consistently. It is not a playable starter game, does not create scenes or prefabs, and does not own example balance.

Use the suite when you want these systems available together:

- gameplay foundation primitives
- persistence and progression foundations
- combat, encounters, attacks, projectiles, and weapon systems
- world spawning and world navigation
- defense-game orchestration
- auto-defense orchestration
- run upgrades and idle progression

The suite intentionally has no meaningful runtime behavior. Namespace `Deucarian.AutoDefenseSuite` is reserved for future tiny validation helpers only if package validation ever needs them.

The playable starter-game foundation belongs in `com.deucarian.template.game.idle-auto-defense`.

## Local Development

Until publication and Package Registry entries exist, add the suite and its dependencies by local file reference in a validation or development project.

```json
{
  "dependencies": {
    "com.deucarian.auto-defense-suite": "file:C:/Repositories/Deucarian/Auto-Defense-Suite"
  }
}
```

Local validation projects should keep explicit file references to unpublished dependencies when needed. The suite package itself declares package ID/version dependencies so the same package can later be published without local paths.

## Install

Stable:

```json
"com.deucarian.auto-defense-suite": "https://github.com/Deucarian/Auto-Defense-Suite.git#main"
```

Development:

```json
"com.deucarian.auto-defense-suite": "https://github.com/Deucarian/Auto-Defense-Suite.git#develop"
```

Use `#main` for stable package consumption and `#develop` when testing active package work.

## When To Use This

Use this package when you need Lean dependency bundle that installs the Deucarian Auto Defense gameplay stack without starter-game content.

Do not use this package to take ownership of capabilities outside its `AGENTS.md` boundary. Reusable behavior should stay with the package that owns that capability in the Package Registry governance docs.

## Quick Start

1. Install the package through Deucarian Package Installer or Unity Package Manager using the URL above.
2. Let Unity finish resolving packages and compiling assemblies.
3. Start from the package README sections above and the public runtime/editor APIs in this repository.

## Troubleshooting

- Package does not resolve: confirm the stable or development Git URL matches the Package Registry entry and that required Deucarian dependencies are installed.
- Unity compile errors after install: let Package Manager finish resolving dependencies, then check asmdef references against `package.json` dependencies.
- Behavior appears to belong in another package: consult `AGENTS.md` and the Package Registry governance docs before moving or duplicating code.
