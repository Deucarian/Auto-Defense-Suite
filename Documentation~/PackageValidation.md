# Package Validation

Unity version: `6000.3.5f1`.

Validation project:

```text
C:\Repositories\Deucarian-Validation\AllPackages-TestProject
```

Package path:

```text
C:\Repositories\Deucarian\Auto-Defense-Suite
```

## Expected Validation

- Suite package imports cleanly by local file reference.
- Shared validation project resolves the suite and the full Auto Defense dependency stack.
- Shared EditMode tests pass twice.
- Shared PlayMode tests pass twice.
- No package runtime dependency on `com.deucarian.test-automation`.
- No UI, Theming, or Unity Entities dependency is introduced.
- No Package Registry changes are made.
- No remotes are added or pushed.

## Shared Validation Manifest Choice

The shared validation project keeps explicit local file references to the underlying packages and adds a local file reference to `com.deucarian.auto-defense-suite`.

This is intentional for local development: the suite declares package ID/version dependencies, while the shared validation manifest supplies local paths for all unpublished packages so Unity can resolve the stack before Package Registry publication.

## Runtime Marker

No runtime marker was added in Phase 1X. The suite validates as a manifest-only dependency bundle.

## Phase 1X Results

Suite package import:

```powershell
C:\Program Files\Unity\Hub\Editor\6000.3.5f1\Editor\Unity.exe -batchmode -nographics -quit -projectPath C:\Repositories\Deucarian-Validation\AllPackages-TestProject -logFile C:\Repositories\Deucarian-Validation\AllPackages-TestProject\Logs\phase1x-suite-import.log
```

- Exit code: `0`
- Log: `C:\Repositories\Deucarian-Validation\AllPackages-TestProject\Logs\phase1x-suite-import.log`
- Result: package registered and imported as `com.deucarian.auto-defense-suite`.
- Notes: Unity logged the recurring licensing token warning and `Curl error 42`; no compiler or package-manager failure was found.

Shared validation import:

```powershell
C:\Program Files\Unity\Hub\Editor\6000.3.5f1\Editor\Unity.exe -batchmode -nographics -quit -projectPath C:\Repositories\Deucarian-Validation\AllPackages-TestProject -logFile C:\Repositories\Deucarian-Validation\AllPackages-TestProject\Logs\phase1x-shared-import.log
```

- Exit code: `0`
- Log: `C:\Repositories\Deucarian-Validation\AllPackages-TestProject\Logs\phase1x-shared-import.log`
- Result: shared validation project resolved the suite by local file reference.

Shared EditMode:

- Pass 1: `46` passed, `0` failed, `0` skipped, `0` inconclusive, duration `1.238` seconds. Results: `C:\Repositories\Deucarian-Validation\AllPackages-TestProject\Logs\phase1x-shared-edit-1.json`.
- Pass 2: `46` passed, `0` failed, `0` skipped, `0` inconclusive, duration `1.220` seconds. Results: `C:\Repositories\Deucarian-Validation\AllPackages-TestProject\Logs\phase1x-shared-edit-2.json`.

Shared PlayMode:

- Pass 1: `2` passed, `0` failed, `0` skipped, `0` inconclusive, duration `2.245` seconds. Results: `C:\Repositories\Deucarian-Validation\AllPackages-TestProject\Logs\phase1x-shared-play-1.json`.
- Pass 2: `2` passed, `0` failed, `0` skipped, `0` inconclusive, duration `2.268` seconds. Results: `C:\Repositories\Deucarian-Validation\AllPackages-TestProject\Logs\phase1x-shared-play-2.json`.

Dependency resolution scan:

- `com.deucarian.auto-defense-suite` resolved from `file:C:/Repositories/Deucarian/Auto-Defense-Suite`.
- All suite dependencies resolved from local file packages in `C:\Repositories\Deucarian`.
- `com.deucarian.test-automation` remains a shared validation project dependency only and is not a suite dependency.
