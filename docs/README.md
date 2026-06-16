# foodup-erp-releases — Documentation Index

Documentation optimized for AI coding agents working on the FoodUp ERP OTA release channel.

## What this repo does

Publishes Android APK updates for **foodup-erp** terminals. The app checks a manifest URL on startup and in Settings to download and install newer APKs.

## Quick reference

| Item | Value |
|------|-------|
| Manifest URL | `https://github.com/JiaYee/foodup-erp-releases/releases/latest/download/version.json` |
| GitHub repo | `JiaYee/foodup-erp-releases` |
| Release script | `scripts/release.ps1` |
| App source | Sibling repo `../foodup-erp` |

## Agent docs

| Document | Contents |
|----------|----------|
| [release-process.md](release-process.md) | Full release workflow, script parameters, prerequisites |
| [manifest.md](manifest.md) | `version.json` schema and OTA client behavior |

## Related repos

| Repo | Role |
|------|------|
| [foodup-erp](../foodup-erp) | App source — builds APK, consumes OTA manifest |
| [foodup-api](../foodup-api) | Backend (no direct coupling to releases) |
| [foodup-admin](../foodup-admin) | Admin dashboard (no direct coupling to releases) |

## Extended docs (in foodup-erp)

| Document | Contents |
|----------|----------|
| [foodup-erp/docs/RELEASES.md](../foodup-erp/docs/RELEASES.md) | Full OTA publish + smoke-test workflow |
| [foodup-erp/docs/ANDROID_RELEASE_SIGNING.md](../foodup-erp/docs/ANDROID_RELEASE_SIGNING.md) | Keystore setup for production APKs |

## Human-readable docs

See also the root [README.md](../README.md).
