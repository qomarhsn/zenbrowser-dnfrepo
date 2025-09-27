# Zen Browser DNF Repository

Automated DNF repository for [Zen Browser](https://github.com/zen-browser/desktop) on Fedora, RHEL, and CentOS systems.

## Quick Install

### 1. Import GPG Key
```bash
sudo rpm --import https://zenbrowser-dnfrepo.qomarhsn.com/RPM-GPG-KEY-zen-browser
```

### 2. Add Repository
```bash
sudo tee /etc/yum.repos.d/zen-browser.repo > /dev/null << 'REPO'
[zen-browser]
name=Zen Browser
baseurl=https://zenbrowser-dnfrepo.qomarhsn.com/
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://zenbrowser-dnfrepo.qomarhsn.com/RPM-GPG-KEY-zen-browser
skip_if_unavailable=True
metadata_expire=6h
REPO
```

### 3. Install Zen Browser
```bash
sudo dnf clean all
sudo dnf install -y zen-browser
```

### 4. Launch
```bash
zen-browser
# or simply (symlinks to zen-browser)
zen
```

## Features

- 🤖 **Automated**: Weekly builds from upstream releases
- 📦 **RPM Package**: Proper system integration
- 🔄 **Auto-Updated**: Tracks latest Zen Browser releases
- 🔒 **GPG Signed**: Cryptographically signed packages and repository metadata
- 🖥️ **Desktop Integration**: Application menu, icons, and file associations
- 🌊 **Wayland Support**: Optimized for modern Linux desktops

## Package Details

| Component | Location |
|-----------|----------|
| Installation | `/opt/zen-browser` |
| Primary Launcher | `/usr/bin/zen-browser` |
| Convenience Symlink | `/usr/bin/zen` → `zen-browser` |
| Desktop Entry | `/usr/share/applications/zen-browser.desktop` |
| Icon | `/usr/share/pixmaps/zen-browser.png` |

## Architecture

- **Supported**: x86_64
- **aarch64 (ARM64)**: Dropped for now to ease management

## How It Works

1. GitHub Actions monitors [zen-browser/desktop](https://github.com/zen-browser/desktop) for new releases
2. Downloads upstream binaries and packages them as RPMs
3. Creates DNF repository metadata
4. Deploys to GitHub Pages at [zenbrowser-dnfrepo.qomarhsn.com](https://zenbrowser-dnfrepo.qomarhsn.com)

## Links

- 🌐 **Website**: [zenbrowser-dnfrepo.qomarhsn.com](https://zenbrowser-dnfrepo.qomarhsn.com)
- 🔧 **Source Code**: [GitHub Repository](https://github.com/qomarhsn/zenbrowser-dnfrepo)
- 🚀 **Upstream**: [Zen Browser](https://github.com/zen-browser/desktop)
- ⚙️ **Build Status**: [GitHub Actions](https://github.com/qomarhsn/zenbrowser-dnfrepo/actions)

---

**Maintained by**: [Qomarul Hasan](https://github.com/qomarhsn) • **License**: MPL-2.0
