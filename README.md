<div align="center">

<img src="snap/gui/bookokrat.png" alt="Bookokrat logo" width="128" />

# Bookokrat

**Read EPUB, PDF and DjVu books in your terminal.**

[![bookokrat](https://snapcraft.io/bookokrat/badge.svg)](https://snapcraft.io/bookokrat)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64, arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [Bookokrat](https://github.com/bugzmanov/bookokrat), a terminal reader for EPUB, PDF and DjVu books with bookmarks, notes and inline images.

</div>

---

## Getting Started

<a href="https://snapcraft.io/bookokrat"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install bookokrat
bookokrat ~/Books/novel.epub
```

Press `?` for keyboard shortcuts. PDF and DjVu pages need a terminal with graphics support, such as Kitty, Ghostty, WezTerm or Konsole.

## Configure

There are no `snap set` options. Change settings in the application with `Space+s`. Data stays inside the snap:

| Data | Location |
| --- | --- |
| Settings | `~/snap/bookokrat/current/.config/bookokrat` |
| Bookmarks and comments | `~/snap/bookokrat/current/.local/share/bookokrat` |
| Image cache and log | `~/snap/bookokrat/current/.cache` and `.local/state` |

For books on removable storage:

```bash
sudo snap connect bookokrat:removable-media
```

## Limitations

- Books must be in a normal folder under your home directory or on connected removable storage. Hidden folders directly under your home directory are not accessible.
- SyncTeX inverse search (`synctex_editor`) cannot start editors installed on the host. Forward search works when the editor runs `bookokrat --synctex-forward` from this snap.
- Bookmarks and settings from a host installation are not read.
- The snap renames the Kitty shared-memory transfer to `snap.bookokrat.*`, which strict confinement requires.

## Build

```bash
git clone https://github.com/sidalit/bookokrat-snap.git
cd bookokrat-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/bookokrat-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/bugzmanov/bookokrat/issues).

## License

Snap packaging: [MIT](LICENSE).
