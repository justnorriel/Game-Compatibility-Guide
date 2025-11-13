# Arch Linux Gaming Setup Guide

This guide covers the installation of essential gaming tools and compatibility layers for Arch Linux.

## Prerequisites

Ensure your system is up to date:
```bash
sudo pacman -Syu
```

## Installation Steps

### 1. Install ProtonUp-Qt and Compatibility Layers

ProtonUp-Qt is a tool for managing Proton and Wine versions for Steam and Lutris.

```bash
sudo pacman -S protonup-qt
```

**Configure the following versions via ProtonUp-Qt:**
- **DXVK**: v2.6.2
- **VKD3D-Proton**: v2.14
- **GE-Proton**: 10-25

#### How to use ProtonUp-Qt:
1. Launch ProtonUp-Qt from your application menu
2. Select Steam or Lutris as the target
3. Click "Add version" and select the desired compatibility tool
4. Choose the specific versions listed above

### 2. Install Lutris

Lutris is a gaming platform that helps manage games from various sources.

```bash
sudo pacman -S lutris
```

## Post-Installation

### Enable Proton in Steam
1. Open Steam
2. Go to **Settings** → **Compatibility**
3. Enable "Enable Steam Play for all other titles"
4. Select your installed GE-Proton version from the dropdown

### Verify Installation
- Launch ProtonUp-Qt to confirm all versions are installed
- Open Lutris and check that runners are available
- Test a game to ensure everything works correctly

## Additional Recommendations

### Optional Dependencies
```bash
# Wine dependencies for better compatibility
sudo pacman -S wine-staging winetricks

# Vulkan support
sudo pacman -S vulkan-icd-loader lib32-vulkan-icd-loader

# Graphics drivers (choose based on your GPU)
# For AMD:
sudo pacman -S vulkan-radeon lib32-vulkan-radeon

# For NVIDIA:
sudo pacman -S nvidia-utils lib32-nvidia-utils

# For Intel:
sudo pacman -S vulkan-intel lib32-vulkan-intel
```

## Troubleshooting

- If games don't launch, ensure you have the correct graphics drivers installed
- Check ProtonDB (www.protondb.com) for game-specific tweaks
- Lutris logs can be found in `~/.local/share/lutris/logs/`

## Resources

- [ProtonDB](https://www.protondb.com/) - Game compatibility database
- [Lutris Documentation](https://lutris.net/docs/)
- [GE-Proton Releases](https://github.com/GloriousEggroll/proton-ge-custom)
- [Arch Wiki - Gaming](https://wiki.archlinux.org/title/Gaming)
