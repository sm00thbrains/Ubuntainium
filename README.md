# Ubuntainium
An idea forged from the frustration of outdated repos and the people who created Obtainium for Android

**Obtainium for Ubuntu** — Update GitHub apps *outside* of `apt`.

No PPAs. No stale repos. No 8-year-old packages.

# THE IDEA

```bash
curl -fsSL get.ubuntainium.sh | bash
ubuntainium add github-project user/github-project deb "github-project_.*amd64\\.deb" \
  "sudo dpkg -i {{file}} || sudo apt install -f -y"
ubuntainium



sudo apt upgrade          → updates Ubuntu
ubuntainium update        → updates WindTerm, Notesnook, Proton Pass, etc.
ubuntainium --offline        → updates from local cache (Wenou ISO)
ubuntainium add windterm     → auto-tracks latest .deb
ubuntainium-up list             → shows all tracked apps
