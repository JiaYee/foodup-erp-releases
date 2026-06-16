# foodup-erp-releases — Agent Guide

**Public Android OTA distribution channel** for FoodUp ERP. This repo holds the update manifest (`version.json`), release automation script, and docs — **not** application source code. APK binaries are published to **GitHub Releases**, never committed to git.

## What this repo is

| Contains | Does not contain |
|----------|------------------|
| `version.json` OTA manifest | Application source code |
| `scripts/release.ps1` automation | `package.json` or npm scripts |
| GitHub Release APK assets | CI / GitHub Actions |
| Release documentation | Electron/desktop builds |

## Tech stack

| Component | Technology |
|-----------|------------|
| Manifest | JSON |
| Release script | PowerShell |
| Publishing | GitHub CLI (`gh release create`) |
| Binary hosting | GitHub Releases |

Build toolchain lives in sibling **foodup-erp** (Expo/React Native Android Gradle).

## Release command

Run from **foodup-erp** root (not this repo):

```powershell
..\foodup-erp-releases\scripts\release.ps1 `
  -VersionName "1.0.20" `
  -VersionCode 20 `
  -Notes "Description of changes."
```

Prerequisites: `gh auth login`, Android release keystore in foodup-erp, both repos as siblings.

## OTA fetch URL

```
https://github.com/JiaYee/foodup-erp-releases/releases/latest/download/version.json
```

Consumed by foodup-erp `src/updates.ts`.

## Gotchas

- **No `package.json`** — don't look for npm scripts here.
- **APKs are gitignored** — stored on GitHub Releases + local `build/` cache.
- **Builds happen in foodup-erp** — this repo only publishes artifacts.
- **`develop` branch is ahead of `main`** — OTA clients use GitHub Release assets, not branch HEAD.
- **Signing is critical** — configured entirely in foodup-erp, not here.
- **sha256 in manifest is not verified** by the app after download.

## Ecosystem

```
foodup-erp ──build APK──► release.ps1 ──publish──► GitHub Releases
foodup-erp ──fetch version.json + APK──► this repo's releases
```

## Documentation

See [docs/README.md](docs/README.md) for the full index.

- [Release process](docs/release-process.md)
- [Manifest schema](docs/manifest.md)

Extended workflow docs in foodup-erp: [docs/RELEASES.md](../foodup-erp/docs/RELEASES.md), [docs/ANDROID_RELEASE_SIGNING.md](../foodup-erp/docs/ANDROID_RELEASE_SIGNING.md).
