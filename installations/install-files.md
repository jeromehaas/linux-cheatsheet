# Install packages and services

## Detect OS

```bash
uname -s             # <- show the operating system type, e.g. Linux or Darwin
cat /etc/os-release  # <- show Linux distribution details like Ubuntu, Fedora, or Arch
```

## macOS with Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"  # <- install Homebrew
brew update                                                                                      # <- update the local Homebrew package metadata
brew install git ripgrep jq                                                                      # <- install common CLI tools
brew install --cask iterm2                                                                       # <- install a macOS desktop app
brew services start nginx                                                                        # <- start nginx as a background service
brew services list                                                                               # <- show managed Homebrew services
```

## Debian / Ubuntu

```bash
sudo apt update                          # <- refresh package lists
sudo apt install -y git curl ripgrep jq  # <- install common CLI tools without prompting
sudo apt install -y nginx                # <- install nginx
sudo systemctl enable --now nginx        # <- enable nginx at boot and start it now
```

## Fedora / RHEL

```bash
sudo dnf install -y git curl ripgrep jq  # <- install common CLI tools without prompting
sudo dnf install -y nginx                # <- install nginx
sudo systemctl enable --now nginx        # <- enable nginx at boot and start it now
```

## Arch

```bash
sudo pacman -Syu                             # <- refresh package database and upgrade the system
sudo pacman -S --needed git curl ripgrep jq  # <- install common CLI tools only if missing
sudo pacman -S --needed nginx                # <- install nginx only if missing
sudo systemctl enable --now nginx            # <- enable nginx at boot and start it now
```
