<p align="center">
  <picture>
    <source media="(prefers-color-scheme: light)" srcset="./assets/openllm-light.svg">
    <img alt="OpenLLM" src="./assets/openllm.svg" width="300">
  </picture>
</p>

<p align="center"><b>OpenLLM for Mac</b> — downloads and updates for the desktop app.</p>

<p align="center">
  <img alt="macOS 12+" src="https://img.shields.io/badge/macOS-12%2B-black.svg">
  <img alt="universal" src="https://img.shields.io/badge/Apple%20silicon%20%2B%20Intel-universal-lightgrey.svg">
  <img alt="notarized" src="https://img.shields.io/badge/Developer%20ID-notarized-success.svg">
</p>

---

Your OpenLLM dashboard in its own window, plus what a browser tab can't do:

- **Connect this Mac in one click.** The app installs the OpenLLM daemon and
  pairs it with your key. No terminal; the key never leaves your Mac.
- **Sign in once.** Google and GitHub sign-ins open in your browser and come
  straight back to the app.
- **Always there.** Menu bar status for this Mac, shortcuts (⌘1–⌘5 for the
  sections, ⌘, for settings), and the app keeps itself up to date.

This repository holds **releases only**; there is no source code here.

## Install

1. Download from **[openllm.sh/download/mac](https://www.openllm.sh/download/mac)**.
2. Open the DMG and drag **OpenLLM** to **Applications**.
3. Open OpenLLM, sign in, and click **Connect this Mac**.

One universal app for Apple silicon and Intel, macOS 12 or later.

## Updates

The app checks [openllm.sh](https://www.openllm.sh) for updates and installs
them itself. Every update is signed; the app refuses one that isn't. The
local daemon updates separately, on its own schedule.

## Verify a download

Each release lists the SHA-256 of every file in `SHA256SUMS`:

```sh
shasum -a 256 ~/Downloads/OpenLLM_*.dmg
```

The app is signed with a Developer ID and notarized by Apple:

```sh
spctl --assess --type execute --verbose /Applications/OpenLLM.app
codesign --verify --deep --strict --verbose=2 /Applications/OpenLLM.app
```

## Beta

**OpenLLM Beta** is for testing against our staging environment,
`dev.openllm.sh`, and is published as a pre-release. Use either OpenLLM or
OpenLLM Beta on a Mac, not both: they share this Mac's daemon.

## Uninstall

Quit OpenLLM (menu bar icon → **Quit OpenLLM**) and move it to the Trash.
The daemon runs without the app; to remove it too:

```sh
openllm uninstall
```

## Help

Questions or problems: [openllm.sh/contact](https://www.openllm.sh/contact).
