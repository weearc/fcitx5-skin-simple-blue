# simple blue
A simple theme build using Inkscape and guided by [Marguerite Su’s tutorial](https://forum.suse.org.cn/t/fcitx-artwork-fcitx/731/15)</br>
<s> A simple theme for fcitx5 modified from [Simple](https://github.com/iovxw/fcitx5-simple-theme) and [Fcitx5 Default](https://github.com/fcitx/fcitx5).</s>

## Screenshot

- InputMethod Change Content</br>
![Content](screenshot/screenshot-content.png)</br>

- Input Horizontal</br>
![horizontal](screenshot/screenshot-input.png)</br>

- Input Vertial</br>
![vertical](screenshot/screenshot-input-vertical.png)</br>

## Install
### Fcitx5
For Arch Linux users:</br>
Try out fcitx5 by using the following command:
```bash
pacman -S fcitx5 fcitx5-qt5 fcitx5-gtk fcitx5-chinese-addons
```
If you have added the `Arch Linux CN Repo`, you can install directly from archlinuxcn.</br>

Then add the following lines:
- xorg: to `~/.xprofile`

```bash
export GTK_IM_MODULE=fcitx5
export XMODIFIERS="@im=fcitx"
export QT_IM_MODULE=fcitx5
fcitx5 > /dev/null &
```

- wayland: to `~/.pam_environment`

```bash
GTK_IM_MODULE DEFAULT=fcitx5
QT_IM_MODULE DEFAULT=fcitx5
XMODIFIERS DEFAULT=@im=fcitx5
```
Also, you should add the following lines to `~/.config/fcitx5/profile`:
```
[Groups/0]
# Group Name
Name=Default
# Layout
Default Layout=us
# Default Input Method
DefaultIM=pinyin

[Groups/0/Items/0]
# Name
Name=keyboard-us
# Layout
Layout=

[Groups/0/Items/1]
# Name
Name=pinyin
# Layout
Layout=

[GroupOrder]
0=Default
```

If you want to change settings in kde system settings, you should install package `fcitx5-kcm`.

### Fcitx5-skin-simple-blue
First, clone the repo to `~/.local/shre/fcitx5/themes/`

```bash
git clone https://github.com/weearc/fcitx5-skin-simple-blue.git  ~/.local/share/fcitx5/themes/simple-blue
```

Add the following to your `~/.config/fcitx5/conf/classicui.conf`

```ini
# True, if you want a vertical candidate list
Vertical Candidate List=False
Theme=simple-blue
```

If using vertical input panel, you'd better replace the file `input_panel.png` with `input_panel_vertical.png` and rename it to `input_panel.png`

**Every time you change the settings please reload fcitx5**

## License

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or distribute this software, either in source code form or as a compiled binary, for any purpose, commercial or non-commercial, and by any means.
