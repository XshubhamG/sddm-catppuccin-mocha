<h1 align='center'>sddm-astronaut-theme</h1>

[sddm-catppuccin-mocha](https://github.com/Keyitdev/sddm-catppuccin-mocha) is a series of themes for the [SDDM](https://github.com/sddm/sddm/) display manager made by **[Xshubhamg](https://github.com/xshubhamg)**.

It's written using the latest version of Qt, which is **Qt6**. Its key features include **virtual keyboard support** and an **installation script**. This theme also support **animated wallpapers**. You can easily change its appearance by choosing another of the ten pre-made themes or creating your own. Each of these themes was created by modifying just one file - **[config](./Themes/catppuccin_street.conf)**.

All themes were created for 1080p. However, they should work well in other resolutions.

## Previews

![Catppuccin street](https://github.com/XshubhamG/sddm-astronaut-theme/blob/main/Previews/catppuccin-street-sddm.png?raw=true)

<p align="center">
    <img src="https://raw.githubusercontent.com/catppuccin/catppuccin/main/assets/palette/macchiato.png"/>
</p>

<details>
<summary><h2>Detailed previews</h2></summary>

|                                                      **Catppuccin street**                                                      |                                                    **Astronaut**                                                     |
| :-----------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------: |
| ![Catppuccin street](https://github.com/XshubhamG/sddm-catppuccin-mocha/blob/main/Previews/catppuccin-street-sddm.png?raw=true) | ![astronaut](https://github.com/Keyitdev/screenshots/blob/master/sddm-astronaut-theme/master/astronaut.png?raw=true) |

</details>

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
sudo git clone -b main --depth 1 https://github.com/xshubhamg/sddm-catppuccin-mocha.git /usr/share/sddm/themes/sddm-catppuccin-mocha
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

This sddm theme is based of [Keyitdev's astronaut sddm themes](https://github.com/Keyitdev/sddm-astronaut-theme). I used it as based
and used background and fonts to match my [dotcat](https://github.com/xshubhamg/dotfiles) configuration. Fonts used in this project are very popular and copied from one user to another, so I don't know who the original creator is.

- Wallpaper arts are taken from [walls-catppuccin-mocha](https://github.com/orangci/walls-catppuccin-mocha)

<p align="center">
	<img src="https://raw.githubusercontent.com/catppuccin/catppuccin/main/assets/footers/gray0_ctp_on_line.svg?sanitize=true" />
</p>

<p align="center">
    <a href="https://github.com/xshubhamg/xshubhamg/LICENSE">
      <img src="https://img.shields.io/static/v1.svg?style=for-the-badge&label=License&message=GPLv3+&logoColor=d9e0ee&colorA=363a4f&colorB=b7bdf8"/>
    </a>
</p>
