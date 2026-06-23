# Dependency Stack

The suite depends on the full Auto Defense gameplay stack.

## Included Dependencies

| Package | Version | Reason |
|---|---:|---|
| `com.deucarian.gameplay-foundation` | 0.1.0 | Shared identifiers, deterministic primitives, tags, stats, clocks, and generic timing. |
| `com.deucarian.persistence` | 0.1.0 | Save/load foundations used by full Auto Defense project setups and future template glue. |
| `com.deucarian.progression` | 0.1.0 | Permanent/meta progression foundations used by full Auto Defense project setups. |
| `com.deucarian.combat` | 0.1.0 | Damage, mitigation, health, shield, and life-state resolution. |
| `com.deucarian.encounters` | 0.1.0 | Wave, group, spawn schedule, and encounter progression primitives. |
| `com.deucarian.world-spawning` | 0.2.0 | Generic spawn requests, spawnables, channels, pooling, and lifecycle cleanup. |
| `com.deucarian.world-navigation` | 0.1.0 | Centralized movement ticking, destination/path following, and spawn cleanup integration. |
| `com.deucarian.defense-games` | 0.1.0 | Defense objective, agent lifecycle, metrics, and genre composition. |
| `com.deucarian.attacks` | 0.1.0 | Attack scheduling, target selection contracts, and attack request orchestration. |
| `com.deucarian.projectiles` | 0.2.0 | Projectile lifecycle, movement, hit resolution integration, and spawning integration. |
| `com.deucarian.weapon-systems` | 0.1.0 | Weapon mounts, runtime configuration, cooldowns, and attack/projectile integration. |
| `com.deucarian.auto-defense` | 0.1.0 | Central-objective Auto Defense orchestration. |
| `com.deucarian.run-upgrades` | 0.1.0 | Run upgrade drafting and selected-upgrade state for Auto Defense runs. |
| `com.deucarian.idle-progression` | 0.1.0 | Offline reward and idle progression primitives. |

## Excluded Dependencies

| Package | Reason |
|---|---|
| `com.deucarian.test-automation` | Validation tooling only. It must not become a gameplay install dependency. |
| `com.deucarian.ui-binding` | UI remains optional and belongs in template content or a later UI integration decision. |
| `com.deucarian.ui-flow` | UI flow remains optional and should not be forced onto toolset users. |
| `com.deucarian.theming` | Theming is presentation infrastructure and belongs in template/UI decisions. |
| `Unity.Entities` | ECS/DOTS integration is out of scope for this suite and should be a future integration/backend package. |

## Why Persistence, Progression, Run Upgrades, and Idle Progression Are Included

The suite is the full Auto Defense install stack, not only the runtime combat loop. Existing Auto Defense starter expectations include save/progression composition, run drafting, and offline rewards. Including these focused packages gives users the whole toolset while still keeping the glue out of the suite runtime.

Adapters that bind these systems into a concrete game should live in the template or future integration packages after repeated use proves they are reusable.
