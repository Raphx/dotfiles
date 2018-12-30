# Dotfiles

dotfiles for Arch Linux.

Setup symlinks:

```
./setup
```

Install system dependencies:

```
pacman -S - < pkglist.txt
```

Install custom build of st terminal:

```
cd st
makepkg -sirc
git clean -f .
```

Start ssh-agent on shell login:

```
systemctl --user enable ssh-agent.service
```

## Maintenance

### pacman packages

To prepare `pkglist.txt`:

```
comm -23 <(pacman -Qqntte | sort) <(pacman -Sqg base base-devel | sort) > pkglist.txt
```

For `pkglist-aur.txt`:

```
pacman -Qqm > pkglist-aur.txt
```

### Fonts

Font configurations are found in multiple locations:

 - `fontconfig/fonts.conf` for global serif, sans, and monospace font configurations on applications that use fontconfig
 - `i3wm/i3-config` for i3 font
 - `st/config.h` for st terminal font
