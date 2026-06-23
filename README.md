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
