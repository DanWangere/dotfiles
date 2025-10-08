# Dotfiles

Personal configuration files for my development environment.

## Contents

This repository contains configuration files for:

- **WezTerm** – Terminal emulator configuration
- **Zsh** – Shell configuration and customizations
- **Aerospace** – Window manager workspace definitions
- **SketchyBar** – macOS status bar, items, and themes
- **JankyBorders** – Window border styling via borders.app

## Structure

```text
dotfiles/
├── aerospace/
│   └── .aerospace.toml                     # Aerospace workspace configuration
├── jankyborders/
│   └── .config/borders/bordersrc           # Borders.app theme
├── sketchybar/
│   └── .config/sketchybar/…                # SketchyBar items, plugins, and themes
├── wezterm/
│   └── .wezterm.lua                        # WezTerm configuration
└── zsh/
    └── .zshrc                              # Zsh shell configuration
```

## Installation

This repository uses [GNU Stow](https://www.gnu.org/software/stow/) for managing symlinks.

### Prerequisites

Install GNU Stow:

```bash
# macOS
brew install stow
```

### Setup

1. Clone this repository (anywhere you like, e.g., `~/source/repos/`):

   ```bash
   git clone https://github.com/Jcardif/dotfiles.git
   cd dotfiles
   ```

2. Use Stow to create symlinks to your home directory:

   ```bash
   # Install all configurations
   stow -vt ~ .
   ```

   ```bash
   # Or install specific configurations
   stow -vt ~ aerospace
   stow -vt ~ jankyborders
   stow -vt ~ sketchybar
   stow -vt ~ wezterm
   stow -vt ~ zsh
   ```

   - `-t ~` = target is your home folder (where symlinks will be created)
   - `-v` = verbose output so you can see what's happening

3. Restart your terminal or source the configurations:

   ```bash
   source ~/.zshrc
   ```

## Uninstallation

To remove symlinks created by Stow:

```bash
cd /path/to/dotfiles
stow -Dvt ~ aerospace
stow -Dvt ~ jankyborders
stow -Dvt ~ sketchybar
stow -Dvt ~ wezterm
stow -Dvt ~ zsh

# Or uninstall all packages at once
stow -Dvt ~ */
```
