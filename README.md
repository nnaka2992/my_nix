# nix

Cross-platform Nix configuration for managing Linux and macOS environments.

## Setup

### 1. Install Nix (multi-user)

```bash
sh <(curl -L https://nixos.org/nix/install) --daemon
```

### 2. Clone and link config

```bash
git clone <repo-url> ~/Dev/nix
ln -s ~/Dev/nix ~/.config/nix
```

### 3. Install Nix-managed packages

```bash
nix profile install ~/.config/nix
```

### 4. Install Claude Code

Claude Code is not available in nixpkgs. Install it manually with the native installer:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

It auto-updates in the background. To update manually: `claude update`.

## Adding or removing packages

Edit the `paths` list in `flake.nix`, then run:

```bash
nix profile upgrade user-packages
```

## Packages

| Package | Source |
|---|---|
| Podman | nixpkgs (Linux only) |
| Mise | nixpkgs |
| Claude Code | native installer |

## Supported Platforms

- **Linux:** x86_64, aarch64
- **macOS:** Apple Silicon (aarch64), Intel (x86_64)
