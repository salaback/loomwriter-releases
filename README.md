# LoomWriter — releases

Public download host for the [LoomWriter](https://loomwriter.app) desktop app.

This repository contains **no source code** — only built installers and the
`tauri-plugin-updater` manifests (`latest.json`). The application source lives in
a private repository; its release pipeline mirrors published artifacts here so
that downloads and auto-updates work without authentication.

## Downloads

Get the latest build from the [**Releases**](https://github.com/salaback/loomwriter-releases/releases)
page, or from the [LoomWriter download page](https://loomwriter.app/download).

| Platform | File |
| --- | --- |
| macOS | `.dmg` (Apple-notarized) |
| Windows | `-setup.exe` (NSIS) or `.msi` |
| Linux | `.AppImage` or `.deb` |

LoomWriter is currently in **beta**; beta builds are published as GitHub
*pre-releases*.

## Auto-update channels

The desktop app updates itself by polling these manifests:

- **prod:** `releases/latest/download/latest.json` — newest non-prerelease.
- **beta:** `releases/download/beta/latest.json` — a single rolling release that
  carries only the manifest; the installer URLs inside it point at the matching
  per-version pre-release.

Releases here are created automatically by the source repo's
`mirror-to-public-releases.yml` workflow when a release is published. Do not
upload assets here by hand.