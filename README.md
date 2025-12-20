# My Dotfiles

This repository contains my personal dotfiles managed with [chezmoi](https://www.chezmoi.io/).

**Note:** This is a private repository. You'll need appropriate authentication set up.

## What's Included

- **Git Configuration** (`dot_gitconfig`) - Git user settings
- **Zsh Configuration** (`dot_zshrc`) - Shell configuration with Oh My Zsh, plugins, and customizations

## Setup

### Prerequisites

For a private repository, ensure you have one of the following set up:
- **SSH keys** configured with GitHub (recommended)
- **Personal Access Token** for HTTPS authentication

### Initial Setup

```bash
# Install chezmoi (if not already installed)
sh -c "$(curl -fsLS get.chezmoi.io)"

# Initialize chezmoi with this repository
# Option 1: Using SSH (recommended for private repos)
chezmoi init git@github.com:YOUR_USERNAME/dotfiles.git

# Option 2: Using HTTPS (requires authentication)
chezmoi init https://github.com/YOUR_USERNAME/dotfiles.git

# Apply the dotfiles
chezmoi apply
```

### On a New Machine

```bash
# Using SSH
chezmoi init --apply git@github.com:YOUR_USERNAME/dotfiles.git

# Or using HTTPS
chezmoi init --apply https://github.com/YOUR_USERNAME/dotfiles.git
```

**Note:** When using HTTPS with a private repo, you may be prompted for credentials. Use a Personal Access Token as the password.

## Usage

```bash
# See what would change
chezmoi diff

# Apply changes
chezmoi apply

# Edit a tracked file
chezmoi edit ~/.zshrc

# Add a new file to track
chezmoi add ~/.somefile

# Remove a file from tracking
chezmoi forget ~/.somefile
```

## Adding New Files

To track a new dotfile:

```bash
chezmoi add ~/.filename
```

## Syncing Changes

```bash
# After making changes, commit and push
chezmoi cd
git add .
git commit -m "Update dotfiles"
git push

# Or use chezmoi's built-in git commands
chezmoi git add .
chezmoi git commit -m "Update dotfiles"
chezmoi git push
```

## Notes

- Files are stored with the `dot_` prefix in this repository
- Use `chezmoi edit` to modify tracked files
- For private repos, ensure your SSH keys or GitHub credentials are configured
- You can check your current remote URL with: `chezmoi git remote -v`

