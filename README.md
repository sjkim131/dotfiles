# Dotfiles

A comprehensive collection of configuration files and setup scripts for creating consistent development environments across multiple platforms including Ubuntu, Cygwin, Synology NAS, and macOS.

## Overview

This repository provides automated installation scripts and configuration files for:
- Shell environments (Bash, Zsh)
- Development tools (Git, Vim, tmux)
- Programming language environments (Python, Go, Rust, C/C++)
- Platform-specific configurations (Ubuntu, Cygwin, Synology)

## Quick Start

### For Ubuntu Systems
```bash
# Install Ubuntu-specific configurations
./install-ubuntu-config.sh

# Optional: Install development packages
cd buildpkg && ./setup.sh
```

### For Other Platforms
```bash
# Cygwin (Windows)
./install-cygwin-config.sh

# Synology NAS
./install-synology-config.sh

# Vim configuration (any platform)
./install-vim-config.sh

# Zsh configuration (any platform)
./install-zsh-config.sh
```

## Directory Structure

### Core Configuration Directories

- **`ubuntu/`** - Ubuntu-specific configuration files
  - Shell configurations (`.bash_aliases`, `.inputrc`, `.tmux.conf`)
  - Development tools (`.gitconfig`, `.clang-format`)
  - Network tools (`.wgetrc`, `.curlrc`, `.axelrc`)
  - Python/pip configuration (`flake8`, `pip.conf`)
  - Font configuration (`fonts.conf`, `local.conf`)
  - APT preferences and configuration

- **`vim/`** - Vim editor configuration
  - Comprehensive `.vimrc` (4500+ lines)
  - Local customizations (`.vimrc.local`)
  - YouCompleteMe configuration (`.ycm_extra_conf.py`)

- **`zsh/`** - Zsh shell configuration
  - Environment setup (`.zshenv`)
  - Interactive shell configuration (`.zshrc`)
  - Keyboard bindings for various terminals (`.zkbd/`)
  - Synology-specific profile

- **`cygwin/`** - Windows Cygwin environment configuration
  - Bash configuration (`.bash_profile`, `.bashrc`)
  - Terminal settings (`.minttyrc`, `.startxwinrc`)
  - Standard tool configurations

- **`synology/`** - Synology NAS configuration
  - Essential tool configurations for NAS environment

### Development Tools

- **`buildpkg/`** - Development environment setup scripts
  - `setup.sh` - Master installation script
  - Individual tool installers:
    - `install-pythonpkgs.sh` - Python packages (virtualenv, black, flake8, etc.)
    - `install-gopkgs.sh` - Go packages
    - `install-rustup.sh` - Rust toolchain
    - `install-git.sh` - Git from source
    - `install-cmake.sh` - CMake build system
    - `install-llvm.sh` - LLVM/Clang compiler
    - `install-vim.sh` - Vim from source
    - `install-tmux.sh` - tmux terminal multiplexer
    - `install-mc.sh` - Midnight Commander file manager
    - `install-cppcheck.sh` - C++ static analysis
  - `patches/` - Source code patches for LLVM and Vim

### Platform Setup

- **`ubuntu-setup/`** - Ubuntu version-specific setup scripts
  - Support for Ubuntu 18.04, 20.04, 20.10, 21.04
  - GNOME Terminal configuration

## Features

### Ubuntu Configuration
- Comprehensive shell aliases and functions
- Optimized terminal input handling
- Development-focused tmux configuration
- Git configuration with sensible defaults
- C/C++ code formatting with clang-format
- Python development environment (flake8, pip configuration)
- Font configuration for better development experience
- APT package management optimization

### Vim Configuration
- Extensive 4500+ line configuration
- YouCompleteMe integration for code completion
- Customizable local settings
- Development-focused plugins and settings

### Zsh Configuration
- Cross-platform compatibility (Linux, macOS, Synology)
- Terminal-specific keyboard bindings
- Automatic shell switching on supported systems
- Environment variable management

### Development Tools
- Automated installation of essential development packages
- Source-based builds for latest versions
- Language-specific package managers (pip, cargo, go modules)
- Code quality tools (linters, formatters, static analyzers)

## Installation Options

### Full Development Environment
```bash
# Install platform configuration
./install-ubuntu-config.sh  # or appropriate platform script

# Install shell configuration
./install-zsh-config.sh

# Install editor configuration
./install-vim-config.sh

# Install development tools
cd buildpkg && ./setup.sh
```

### Selective Installation
You can install components individually:
```bash
# Just shell and basic tools
./install-ubuntu-config.sh

# Add advanced editor setup
./install-vim-config.sh

# Add specific development tools
cd buildpkg && ./install-pythonpkgs.sh
```

## Requirements

- **Ubuntu**: Requires sudo access for system-wide configurations
- **Cygwin**: Standard Cygwin installation
- **Synology**: SSH access to Synology NAS
- **General**: Bash or Zsh shell, basic Unix utilities

## Notes

- The Ubuntu installer (`install-ubuntu-config.sh`) supports a `--force` flag to overwrite existing configurations
- Many build scripts create optimized builds from source for better performance
- The repository is designed for modular use - install only what you need
- Some development tools may require significant compilation time
- Review scripts before running to understand system changes

## Compatibility

- **Tested on**: Ubuntu 18.04+, Cygwin, Synology DSM, macOS
- **Shells**: Bash, Zsh
- **Terminals**: xterm, screen, tmux, GNOME Terminal, mintty

## Contributing

When adding new configurations:
1. Follow the existing directory structure
2. Create platform-specific versions when needed
3. Update installation scripts accordingly
4. Test on target platforms before committing
