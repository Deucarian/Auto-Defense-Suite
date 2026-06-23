# Auto Defense Suite

`com.deucarian.auto-defense-suite` is a suite package.

Suite means dependency bundle / install stack. It installs a coherent set of packages but should contain little or no runtime code.

## What It Installs

The suite installs the reusable Auto Defense toolset:

- `com.deucarian.gameplay-foundation`
- `com.deucarian.persistence`
- `com.deucarian.progression`
- `com.deucarian.combat`
- `com.deucarian.encounters`
- `com.deucarian.world-spawning`
- `com.deucarian.world-navigation`
- `com.deucarian.defense-games`
- `com.deucarian.attacks`
- `com.deucarian.projectiles`
- `com.deucarian.weapon-systems`
- `com.deucarian.auto-defense`
- `com.deucarian.run-upgrades`
- `com.deucarian.idle-progression`

## Why It Exists

Users who already have a Unity project should not have to know the complete stack order by memory. The suite gives those users one package to install when they want the Auto Defense systems available.

The suite is especially useful before the template exists, because it gives development projects, validation projects, and eventual Package Registry users a single install target for the toolset.

## What It Does Not Own

The suite does not own:

- scenes
- prefabs
- placeholder art or audio
- example balance
- enemies, weapons, modules, or catalogs
- starter UI
- setup wizards
- save-game glue code
- offline reward glue code
- run upgrade adapters
- gameplay samples beyond tiny install validation, if ever needed

Those belong in focused packages, integrations, samples, or the future template.

## Runtime Code Policy

The suite currently has no runtime assembly.

Namespace `Deucarian.AutoDefenseSuite` is reserved for a future tiny marker or install-validation helper only if Unity validation proves one is useful. Meaningful gameplay behavior must stay in focused packages.
