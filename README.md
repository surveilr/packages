# Surveilr Package Repository

This repository contains DALEC-generated packages for surveilr, providing native installation options across multiple platforms.

## Installation

### 📦 Package Managers (Recommended)

#### Ubuntu/Debian (.deb packages)

```bash
# Ubuntu (Jammy)
wget https://github.com/surveilr/packages/releases/latest/download/surveilr_jammy.deb
sudo dpkg -i surveilr_jammy.deb

# Debian (Bookworm)
wget https://github.com/surveilr/packages/releases/latest/download/surveilr_bookworm.deb
sudo dpkg -i surveilr_bookworm.deb
```

#### macOS (Homebrew)

```bash
brew tap surveilr/tap && brew install surveilr
```

#### Windows

```powershell
# Recommended: Use installation script
irm https://raw.githubusercontent.com/surveilr/packages/refs/heads/main/scripts/install.ps1 | iex

# Alternative: Direct download
# Download from: https://github.com/surveilr/packages/releases/latest
```

### 🔗 Direct Download

Visit our [GitHub Releases](https://github.com/surveilr/packages/releases) page to download pre-built binaries for your operating system:

- **Windows**: `surveilr-windows.zip`
- **macOS**: `surveilr-macos.zip`
- **Linux**: `surveilr-linux.tar.gz`

### 📜 Installation Scripts (Legacy)

For backward compatibility, you can still use the installation scripts:

#### macOS and Linux

```bash
# Install in current directory
curl -sL https://raw.githubusercontent.com/surveilr/packages/main/surveilr/install.sh | bash

# Install globally
curl -sL https://raw.githubusercontent.com/surveilr/packages/main/surveilr/install.sh | SURVEILR_HOME="$HOME/bin" bash

# Install in custom directory
curl -sL https://raw.githubusercontent.com/surveilr/packages/main/surveilr/install.sh | SURVEILR_HOME="/path/to/directory" bash
```

### 🛠️ Alternative Installation (Eget)

```bash
# Install eget first
curl https://zyedidia.github.io/eget.sh | sh

# Install surveilr
eget surveilr/packages --asset tar.gz
```

## Verification

After installation, verify that `surveilr` is working correctly:

```bash
surveilr --version                      # Show version information
surveilr doctor                         # Check dependencies
surveilr --help                         # Display help information
```

For more commands, see the [CLI reference](https://docs.opsfolio.com/surveilr/reference/cli/commands/).

## Updates

### Upgrading

```bash
# Upgrade to latest version
surveilr upgrade

# Upgrade to specific version
surveilr upgrade -v 3.2.0

# Skip confirmation prompt
surveilr upgrade --yes
```

### Package Manager Updates

If you installed via package managers, you can also update using:

```bash
# Ubuntu/Debian
sudo apt update && sudo apt upgrade surveilr

# macOS
brew upgrade surveilr
```

## Release Information

This repository is powered by [DALEC](https://github.com/Azure/dalec) for automated package generation and distribution. Each release includes:

- **Ubuntu packages** (.deb for jammy)
- **Debian packages** (.deb for bookworm) 
- **Windows binaries** (.zip)
- **macOS binaries** (.zip)
- **Linux binaries** (.tar.gz)
- **Homebrew formula** (macOS)

For the latest release notes, visit [GitHub Releases](https://github.com/surveilr/packages/releases).

---

**Note**: This replaces the previous release system from `releases.opsfolio.com`. All new installations should use the packages from this repository.