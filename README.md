# Deucarian Auto Defense Suite

`com.deucarian.auto-defense-suite` is an install stack for Deucarian Auto Defense projects.

The suite exists for teams that already have a Unity project and want the full Auto Defense toolset installed consistently. It is not a playable starter game and does not own product balance. Its imported Basic Auto Defense sample is a generic composition check for the packages installed by the suite.

Use the suite when you want these systems available together:

- gameplay foundation primitives
- persistence and progression foundations
- combat, encounters, attacks, projectiles, and weapon systems
- world spawning and world navigation
- defense-game orchestration
- auto-defense orchestration
- run upgrades and idle progression

The suite intentionally has no production runtime behavior. The sample assembly is isolated under `Samples~` and exists only when a user imports the composition example.

The playable starter-game foundation belongs in `com.deucarian.template.game.idle-auto-defense`.

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

Use this package when you need a lean dependency bundle that installs the Deucarian Auto Defense gameplay stack without starter-game content. Import Basic Auto Defense Composition from Package Manager when you want to verify the complete stack in a disposable scene.

Do not use this package to take ownership of capabilities outside its `AGENTS.md` boundary. Reusable behavior should stay with the package that owns that capability in the Package Registry governance docs.

## Quick Start

1. Install the package through Deucarian Package Installer or Unity Package Manager using the URL above.
2. Let Unity finish resolving packages and compiling assemblies.
3. Optionally import Basic Auto Defense Composition and open `BasicAutoDefense.unity`.
4. Build product-specific content with the public APIs owned by the focused packages.

## Troubleshooting

- Package does not resolve: confirm the stable or development Git URL matches the Package Registry entry and that required Deucarian dependencies are installed.
- Unity compile errors after install: let Package Manager finish resolving dependencies, then check asmdef references against `package.json` dependencies.
- Behavior appears to belong in another package: consult `AGENTS.md` and the Package Registry governance docs before moving or duplicating code.

## Validation

Run the shared package validator from this repository root:

```powershell
python C:/Repositories/Package-Registry/Tools/deucarian_package_validator.py --registry-root C:/Repositories/Package-Registry --repository-root . --config deucarian-package.json
```

Documentation-only updates should still pass:

```powershell
git diff --check
```

## License

MIT. See `LICENSE.md`.
