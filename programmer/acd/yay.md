# yay

## Installing And Using The Yay AUR Helper - YouTube d

```txt
sudo pacman -S git
git clone https://aur.archlinux.org/yay.git
cd yay
ls
  PKGBUILD
makepkg -si

man yay
yay -S git
yay -S ddgr

yay -Ss xmonad                 s = search
yay -Si xmonad                 i = information


yay -Syu                       update
yay -Sua                       update aur

yay -Pu                        list of packages

yay -Yc                        remove unwanted dependencies
yay -Rns ddgr                  remove package and dependencies
```

