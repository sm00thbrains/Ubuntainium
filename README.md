# Ubuntainium

[![GitHub stars](https://img.shields.io/github/stars/sm00thbrains/Ubuntainium)](https://github.com/sm00thbrains/Ubuntainium/stars)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Obtainium for Ubuntu** — Update GitHub apps *outside* of `apt`. No PPAs. No stale repos. No 8-year-old packages haunting your system.

Tired of Ubuntu's repos lagging years behind? Ubuntainium watches GitHub releases and auto-updates your tools. `.deb`, `.AppImage`, binaries — all handled.

bash
curl -fsSL get.ubuntainium.sh | bash
ubuntainium add windterm kingToolbox/WindTerm deb "WindTerm_.*amd64\\.deb" \
  "sudo dpkg -i {{file}} || sudo apt install -f -y"
ubuntainium  # Updates everything


**Why Ubuntainium?**

Fresh Updates:    Devs ship weekly? You get 'em today — not in 2029.
Offline-Ready:    Cache downloads for air-gapped setups (Wenou ISO vibes).
Zero Bloat:       Bash + curl + jq. No daemons, no telemetry.
Hook into Apt:    sudo apt upgrade → auto-triggers ubuntainium.

**Features**

[![GitHub stars](https://img.shields.io/github/stars/sm00thbrains/Ubuntainium)](https://github.com/sm00thbrains/Ubuntainium/stars)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Obtainium for Ubuntu** — Update GitHub apps *outside* of `apt`. No PPAs. No stale repos. No 8-year-old packages haunting your system.

Tired of Ubuntu's repos lagging years behind? Ubuntainium watches GitHub releases and auto-updates your tools. `.deb`, `.AppImage`, binaries — all handled.

```bash
curl -fsSL get.ubuntainium.sh | bash
ubuntainium add windterm kingToolbox/WindTerm deb "WindTerm_.*amd64\\.deb" \
  "sudo dpkg -i {{file}} || sudo apt install -f -y"
ubuntainium  # Updates everything
```

## Why Ubuntainium?

- **Fresh Updates**: Devs ship weekly? You get 'em *today* — not in 2029.
- **Offline-Ready**: Cache downloads for air-gapped setups (Wenou ISO vibes).
- **Zero Bloat**: Bash + curl + jq. No daemons, no telemetry.
- **Hook into Apt**: `sudo apt upgrade` → auto-triggers `ubuntainium`.

## Features

| Feature | Status |
|---------|--------|
| `ubuntainium` → updates all | ✅ Done |
| `ubuntainium update windterm` | ✅ Done |
| `ubuntainium add` | ✅ Done |
| `ubuntainium --offline` | ✅ Done |
| Apt post-hook | ✅ Done |
| `.deb`, `.AppImage`, `tar.gz` | ✅ Done |
| Wenou ISO integration | ✅ Done |

## Quickstart Config

Drop this in `~/.config/ubuntainium/apps.json` for instant wins:

```json
[
  {
    "name": "WindTerm",
    "repo": "kingToolbox/WindTerm",
    "type": "deb",
    "pattern": "WindTerm_.*amd64\\.deb",
    "install_cmd": "sudo dpkg -i {{file}} || sudo apt install -f -y"
  },
  {
    "name": "Notesnook",
    "repo": "streetwriters/notesnook",
    "type": "appimage",
    "pattern": "notesnook_linux_x86_64.AppImage",
    "install_cmd": "mkdir -p ~/Applications && cp {{file}} ~/Applications/notesnook.AppImage && chmod +x ~/Applications/notesnook.AppImage"
  }
]
```

## Install

```bash
curl -fsSL get.ubuntainium.sh | bash
```

## Add an App

```bash
ubuntainium add windterm kingToolbox/WindTerm deb "WindTerm_.*amd64\\.deb" \
  "sudo dpkg -i {{file}} || sudo apt install -f -y"
```

## Wenou ISO

Pre-cache:
```bash
ubuntainium  # Downloads latest
cp -r ~/.config/ubuntainium ~/.cache/ubuntainium /path/to/iso/rootfs/home/user/
```

First boot:
```bash
ubuntainium --offline
```

## License

MIT — Free forever.

---

> **"They said Linux updates were slow. We said: Hold my Ubuntainium."**

