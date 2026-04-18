# foodup-erp-releases

Public release artifacts for **FoodUp ERP** (Android APKs and update manifest).

Application source code lives in a private repository; this repo exists only to host **versioned APK downloads** and `version.json` for over-the-air updates.

## Manifest URL (used by the app)

```
https://github.com/JiaYee/foodup-erp-releases/releases/latest/download/version.json
```

## Publishing a release

From the app project (`foodup-erp` sibling folder), run:

```powershell
..\foodup-erp-releases\scripts\release.ps1 `
  -VersionName "1.0.5" `
  -VersionCode 5 `
  -Notes "Bug fixes and improvements."
```

Prerequisites:

1. [GitHub CLI](https://cli.github.com/) installed and authenticated: `gh auth login`
2. Android release signing configured (see `foodup-erp/docs/ANDROID_RELEASE_SIGNING.md`)

See also [../foodup-erp/docs/RELEASES.md](../foodup-erp/docs/RELEASES.md) in the app repo.
