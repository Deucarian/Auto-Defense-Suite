# Deucarian Auto Defense Suite Agent Notes

Package ID: `com.deucarian.auto-defense-suite`
Repository: `Deucarian/Auto-Defense-Suite`

Follow the canonical Deucarian governance docs in [Package Registry](https://github.com/Deucarian/Package-Registry/blob/main/ARCHITECTURE.md), especially capability ownership and dependency rules.

## Ownership

This package owns:

- Dependency composition for the lean Deucarian Auto Defense gameplay stack.

Registered capabilities:
- None.

This package must not own:

- Runtime gameplay implementation, product starter scenes, template content, editor authoring frameworks, package installation behavior, registry governance, template-specific balance, or product logic.

## Dependencies

Allowed dependency shape:

- Suite-only package that declares the direct dependency stack it installs.

Required dependencies and why:

- `com.deucarian.gameplay-foundation`: shared gameplay primitives.
- `com.deucarian.persistence`: save/load foundation for auto-defense projects.
- `com.deucarian.progression`: progression and reward foundations.
- `com.deucarian.combat`: combat simulation foundations.
- `com.deucarian.encounters`: encounter and wave foundations.
- `com.deucarian.world-spawning`: spawned world objects.
- `com.deucarian.world-navigation`: spawned object navigation.
- `com.deucarian.defense-games`: generic defense-game orchestration.
- `com.deucarian.attacks`: attack definitions and target evaluation.
- `com.deucarian.projectiles`: projectile lifecycle support.
- `com.deucarian.weapon-systems`: weapon orchestration.
- `com.deucarian.auto-defense`: auto-defense framework orchestration.
- `com.deucarian.run-upgrades`: run upgrade drafting and effects.
- `com.deucarian.idle-progression`: offline/idle progression helpers.

Optional/version-defined dependencies:

- None.

Architecture exceptions:

- None.

## Policies

- Keep the suite lean and behavior-free.
- Own the generic multi-package composition sample required by the suite sample contract.
- Do not add runtime assemblies, editor UI, product/template scenes, or local copies of lower-package helpers.
- Update `package.json`, `deucarian-package.json`, Package Registry, and fallback catalogs together if the suite dependency list changes.
- Logging: Do not introduce direct Unity Debug calls.
- Unity object lifetime: This package should not own Unity object cleanup.
- Testing: Validate dependency metadata and install behavior through shared package validation.

## Validation

Run the shared validator before committing:

```powershell
python C:/Repositories/Package-Registry/Tools/deucarian_package_validator.py --registry-root C:/Repositories/Package-Registry --repository-root . --config deucarian-package.json
```

Documentation-only updates should still run `git diff --check`.

## Codex Guidance

- Inspect current files before changing anything.
- Work on `develop`; do not edit or merge `main` unless the task is promotion-only.
- Do not edit `Library/PackageCache`.
- Do not guess package versions or dependency versions.
- Do not add package dependencies casually; update asmdefs, `package.json`, `deucarian-package.json`, Package Registry, Package Installer fallback, and Bootstrap fallback together when a dependency is truly required.
- Do not create local copies of shared helpers.
- Keep commits focused and report exactly what changed and what was validated.
