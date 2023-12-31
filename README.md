## Contents

- [Contents](#contents)
- [Installation](#installation)
- [Remember](#remember)
- [Important Dependencies](#important-dependencies)
- [Manual AUR Packages](#manual-aur-packages)
- [Enable Snap](#enable-snap)
- [Snap Packages](#snap-packages)
- [Rofi Theme](#rofi-theme)
- [Ulauncher Theme](#ulauncher-theme)
- [Dotly](#dotly)
- [Sdkman](#sdkman)
- [Fix QT Theme](#fix-qt-theme)
- [nwgbar-icons](#nwgbar-icons)
- [Vlang (optional)](#vlang-optional)
- [Sddm (optional)](#sddm-optional)
- [Wifi Drivers (optional)](#wifi-drivers-optional)

## Installation
```bash
git clone https://github.com/LR56c/garuda-hyprland-pc-config.git && \
cp -r garuda-hyprland-pc-config/* ~/.config
```

## Remember
- [wallpapers drive](https://drive.google.com/drive/folders/1ZyZNp6Md5Gx8ghSbyd6rbU-kC3SYT3gc?usp=sharing)
- setup qt and gtk theme +font
- setup ulauncher theme
- [setup discord manual](https://discord.com/api/download?platform=linux&format=tar.gz) 
  - [Install BetterDiscord](https://betterdiscord.app/) 
  - setup application search in rofi/ulauncher
    - copy discord.desktop file in `/<discord_path>/Discord` to: `/home/lr56c/.local/share/applications/discord.desktop`
      - add: `Exec=/<discord_path>/Discord`

- jetbrains config +plugins_list
```bash
https://github.com/LR56c/jetbrains_ide_settings
```

## Important Dependencies
```bash
sudo chmod +x ~/.config/deps_install.sh
```
```bash
sudo sh ~/.config/deps_install.sh
```

## Manual AUR Packages
- recommend pamac-aur (GUI)
```bash
anyrun-git
```
```bash
exercism-bin
```
```bash
hyprland-autoname-workspaces-git
```
```bash
hyprpicker
```
```bash
rofi-file-browser-extended-git
```
```bash
snapd
```
```bash
textsnatcher
```
```bash
xwaylandvideobridge-cursor-mode-2-git
```
```bash
pyprland
```
```bash
appimagelauncher
```
```bash
emote
```
```bash
pieces-os
```
```bash
pieces-for-developers
```

## Enable Snap
```bash
sudo systemctl enable --now snapd.socket && \
sudo ln -s /var/lib/snapd/snap /snap
```

## Snap Packages
```bash
sudo snap install nvim --classic
```
```bash
sudo snap install flutter --classic
```
- optionals
```bash
sudo snap install pieces-os
```
```bash
sudo snap install pieces-for-developers
```

## Rofi Theme
```bash
git clone https://github.com/lr-tech/rofi-themes-collection.git && \
cd rofi-themes-collection && \
mkdir -p ~/.local/share/rofi/themes/ && \
cp themes/spotlight-dark.rasi  ~/.local/share/rofi/themes/
```
```bash
cd ~/.config/custom-themes/catpuccin && \
git clone https://github.com/catppuccin/rofi/ && \
cd rofi/basic && \
sh install.sh
```

## Ulauncher Theme
```bash
mkdir -p ~/.config/ulauncher/user-themes
```
```bash
git clone https://github.com/Raayib/WhiteSur-Dark-ulauncher.git \
  ~/.config/ulauncher/user-themes/WhiteSur-Dark-ulauncher
```
## Dotly
```bash
bash <(curl -s https://raw.githubusercontent.com/CodelyTV/dotly/HEAD/installer)
```
- in `garuda-hyprland-pc-config` folder:
```bash
cp .zshrc ~
```

## Sdkman
```bash
curl -s "https://get.sdkman.io" | bash
```

## Fix QT Theme
file: `/etc/environment`
```bash
QT_QPA_PLATFORMTHEME=qt5ct
```

## nwgbar-icons
```bash
cd ~/.config/custom-themes/catpuccin/nwgbar-icons
```
```bash
sudo sh install.sh
```

## Vlang (optional)
```bash
git clone https://github.com/vlang/v && \
cd v && \
make
```

## Sddm (optional)
```bash
sudo cp -r ~/.config/custom-themes/sddm/sober /usr/share/sddm/themes/
```
- file: `/usr/lib/sddm/sddm.conf.d/default.conf` or `/etc/sddm.conf`
```bash
[Theme]
Current=sober
```

## Wifi Drivers (optional)
```bash
mkdir drivers && \
 cd drivers && \
 git clone https://github.com/aircrack-ng/rtl8812au.git && \
 cd rtl8812au && \
 sudo make dkms_install
```
