# Hyprland Configuration Files

Arch and Fedora linux are the two linux versions of focus.

## Installation for fedora

Ensure wayland is intalled
```
$ sudo dnf install hyprland
```

Note: Screenshot is of fedora/hypr development environment.
![Screenshot](20230916_11h04m09s_grim.png)

## Installation for arch

Ensure base-devel is installed before proceeding

Note: Screenshot is of arch/hypr development environment.
![Screenshot](20230916_19h33m35s_grim.png)


### Yay

**Important**: Execute the following commands as a regular user, NOT as root!

```
git clone https://aur.archlinux.org/yay-bin
cd yay-bin
makepkg -si
```

### Required Packages

``` bash
yay -S hyprland polkit-gnome ffmpeg neovim viewnior rofi      \
pavucontrol thunar starship wl-clipboard wf-recorder swaybg   \
grimblast-git ffmpegthumbnailer tumbler playerctl             \
noise-suppression-for-voice thunar-archive-plugin kitty       \
waybar-hyprland wlogout swaylock-effects sddm-git pamixer     \
nwg-look-bin nordic-theme papirus-icon-theme dunst otf-sora   \
ttf-nerd-fonts-symbols-common otf-firamono-nerd inter-font    \
ttf-fantasque-nerd noto-fonts noto-fonts-emoji ttf-comfortaa  \
ttf-jetbrains-mono-nerd ttf-icomoon-feather ttf-iosevka-nerd  \
adobe-source-code-pro-fonts brightnessctl hyprpicker-git
```
- If you are getting **[error 4 related with payload and client.cpp](https://github.com/Alexays/Waybar/issues/2159)** while building waybar-hyprland-git download PKGBUILD and enter this code in build() section:
``` sed -i '10 i #include <stdexcept>\n#include <string>' include/modules/sway/ipc/client.hpp ``` then build (```makepkg -si```)


## Important Notes

- It is recommended to use `archinstall` with Sway as the desktop environment for the base installation.
- `SDDM-GIT` is required to avoid shutdown bugs and delays.
- Configure SDDM for autologin (for security, use `swaylock` at the beginning of the script).
- Replace `xdg-desktop-portal-wlr` with **[xdg-desktop-portal-hyprland-git](https://wiki.hyprland.org/hyprland-wiki/pages/Useful-Utilities/Hyprland-desktop-portal/)**.

## Known Issues

- Hyprland is in beta (version 0.28) at the time of creating these configuration files.
- Occasionally, windows on the RX6700XT may become distorted and require a reload.

## Roadmap

- [ ] Hotkey for Help Popup
- [ ] Wayland guide for nwg-look, wlr-randr, etc.
- [ ] Synergy Workaround - Exploring waynergy or KVM usage
- [ ] Gamescope Integration - Enhancing compatibility with Steamdeck features
- [ ] Additional Customizations for Waybar - Battery, Backlight, etc.
- [ ] Automatic Configuration - Long-term goal

## References

- Official Hyprland GitHub: <https://github.com/hyprwm/Hyprland>
- Linux Mobiles Hyprland Configuration Files: <https://github.com/linuxmobile/hyprland-dots>
