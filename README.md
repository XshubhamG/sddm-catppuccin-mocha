# sddm-astronaut-theme

[sddm-catppuccin-mocha](https://github.com/Keyitdev/sddm-catppuccin-mocha) is a series of themes for the [SDDM](https://github.com/sddm/sddm/) display manager made by **[Xshubhamg](https://github.com/xshubhamg)**.

It's written using the latest version of Qt, which is **Qt6**. Its key features include **virtual keyboard support** and an **installation script**. This theme also support **animated wallpapers**. You can easily change its appearance by choosing another of the ten pre-made themes or creating your own. Each of these themes was created by modifying just one file - **[config](./Themes/catppuccin_street.conf)**.

All themes were created for 1080p. However, they should work well in other resolutions.

## Preview of animated themes

![Catppuccin street](https://github.com/XshubhamG/sddm-astronaut-theme/blob/main/Previews/catppuccin-street-sddm.png?raw=true)

## Installation

### Automatic Installation

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/xshubhamg/sddm-catppuccin-mocha/main/setup.sh)"
```

> Works on distributions using pacman, xbps-install, dnf, zypper.
> Remember to always read the scripts you run from the internet.

### Manual Installation

1. Install **dependencies**

[`sddm >= 0.21.0`](https://github.com/sddm/sddm), [`qt6 >= 6.8`](https://doc.qt.io/qt-6/index.html), [`qt6-svg >= 6.8`](https://doc.qt.io/qt-6/qtsvg-index.html), [`qt6-virtualkeyboard >= 6.8`](https://doc.qt.io/qt-6/qtvirtualkeyboard-index.html), [`qt6-multimedia >= 6.8`](https://doc.qt.io/qt-6/qtmultimedia-index.html)

You may also want to install additional video codecs like h.264.

```sh
sddm qt6-svg qt6-virtualkeyboard qt6-multimedia-ffmpeg     # Arch
sddm qt6-svg qt6-virtualkeyboard qt6-multimedia            # Void
sddm qt6-qtsvg qt6-qtvirtualkeyboard qt6-qtmultimedia      # Fedora
sddm-qt6 libQt6Svg6 qt6-virtualkeyboard qt6-virtualkeyboard-imports qt6-multimedia qt6-multimedia-imports        # OpenSUSE
```

2. Clone this repository

```sh
sudo git clone -b master --depth 1 https://github.com/xshubhamg/sddm-catppuccin-mocha.git /usr/share/sddm/themes/sddm-catppuccin-mocha
```

3. Copy fonts to `/usr/share/fonts/`

```sh
sudo cp -r /usr/share/sddm/themes/sddm-catppuccin-mocha/Fonts/* /usr/share/fonts/
```

4. Edit `/etc/sddm.conf`

```sh
echo "[Theme]
Current=sddm-catppuccin-mocha" | sudo tee /etc/sddm.conf
```

5. Edit `/etc/sddm.conf.d/virtualkbd.conf`

```sh
echo "[General]
InputMethod=qtvirtualkeyboard" | sudo tee /etc/sddm.conf.d/virtualkbd.conf
```

## Selecting a theme

You can select theme by editing [metadata](./metadata.desktop) (`/usr/share/sddm/themes/sddm-astronaut-theme/metadata.desktop`).

Just edit this line:

```
ConfigFile=Themes/catppuccin_street.conf
```

All available configs are in [Themes](./Themes/) directory.

## Previewing a theme

You can preview the set theme without logging out by runnning:

```sh
sddm-greeter-qt6 --test-mode --theme /usr/share/sddm/themes/sddm-catppuccin-mocha/
```

> Note that depending on the system configuration, the preview may differ slightly from the actual login screen.

## Sources

## Supporting project

You can support me simply by dropping a **star** on **[github](https://github.com/Keyitdev/sddm-astronaut-theme)**

Distributed under the **[GPLv3+](https://www.gnu.org/licenses/gpl-3.0.html) License**.
Copyright (C) 2022-2025 Keyitdev.
