# heca-artifacts

Public download mirror for [heca](https://heca.sh) release artifacts. Builds run
in the private `getheca/heca` repository; release CI uploads the resulting
assets here so they can be downloaded without authentication.

## Getting started

To use heca, first install it on the machine where your work lives. Most
users should install the [desktop app](#desktop-app); advanced users who
want to run heca on a server or without a GUI can set up the
[headless CLI](#headless-cli) instead.

Once a machine is running heca (as either the desktop app or the headless
CLI), it becomes a heca host that you can also control remotely from the
[web app](#web-app).

## Desktop app

The recommended way to run heca on your own machine. Download the latest
desktop app:

macOS (Apple Silicon):

```text
https://releases.heca.sh/heca-latest-macos-aarch64.dmg
```

Linux (x86_64):

```text
https://releases.heca.sh/heca-latest-linux-x86_64.AppImage
```

## Headless CLI

For advanced users: run heca without a GUI, for example on a remote server.
Each release ships the headless CLI bundle for Linux (x86_64, aarch64) and
macOS (arm64, x86_64): the `heca` command-line client plus its sibling
`heca-daemon` and `heca-mcp-server` binaries, with a sha256 checksum manifest.

Install the latest release:

```sh
curl -fsSL https://github.com/getheca/heca-artifacts/releases/latest/download/install-cli.sh | sh
```

The installer verifies checksums and installs into `~/.local/bin` by default.
Set `HECA_INSTALL_DIR` to change the destination, or `HECA_CLI_VERSION` to pin
a release tag. Stable per-platform URLs:

```text
https://github.com/getheca/heca-artifacts/releases/latest/download/heca-cli-linux-x86_64.tar.gz
https://github.com/getheca/heca-artifacts/releases/latest/download/heca-cli-linux-aarch64.tar.gz
https://github.com/getheca/heca-artifacts/releases/latest/download/heca-cli-macos-arm64.tar.gz
https://github.com/getheca/heca-artifacts/releases/latest/download/heca-cli-macos-x86_64.tar.gz
```

Versioned archives stay available under `releases/download/<tag>/`.

After installing, sign in to NyxID and start the daemon:

```sh
heca login
heca daemon start
```

## Web app

[app.heca.sh](https://app.heca.sh) lets you remotely control your heca hosts
from the browser, signed in with NyxID. It is not a standalone way to run
heca: you need at least one machine already running the desktop app or the
headless CLI before the web app can do anything.

## Repository contents

This repository intentionally contains no source code. Releases and their
assets are the product; other heca artifact types may be published here in
the future. Source lives in the main heca repositories.

## Reporting issues

Found a bug or have a feature request? File it at
[getheca/heca-issues](https://github.com/getheca/heca-issues).
