# Dotfiles

dotfiles for non-graphical Arch Linux in virtual machine.

Setup symlinks:

```
./setup
```

Install system dependencies:

```
pacman -S --needed - < pkglist.txt
```

Install AUR packages manually, each installation is done with:

```
makepkg -sirc
```

Enable user systemd services:

```
systemctl --user enable ssh-agent.service
```

Install vim plugins:

```
bin/vv install < vim-plugins
```

## Maintenance

### pacman packages

To prepare `pkglist.txt`:

```
comm -23 <(pacman -Qqntte | sort) <(pacman -Sqg base-devel | sort) > pkglist.txt
```

For `pkglist-aur.txt`:

```
pacman -Qqm > pkglist-aur.txt
```

### vim plugins

Prepare `vim-plugins`:

```
bin/vv dump > vim-plugins
```
