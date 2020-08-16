# aur

## AUR How To Install Arch Software With And Without A Helper - YouTube d

```txt
https://wiki.archlinux.org/index.php/AUR_helpers

man yay
yay discord
  11
yay -Syu

yay -Sua
  1

yay -S lf
  1



firefox
  yay aur
git clone https://aur.archlinux.org/yay.git
lf
cd yay
lf
  PKGBUILD
man makepkg
makepkg -si
```

## How to install AUR packages (manually + helpers) - YouTube d

```txt
aur
  arch user repository
  51549 packages


sudo pacman -S --needed base-devel git

sudo vi /etc/makepkg.conf
  MAKEFLAGS="-j$(nproc)"
nproc


https://aur.archliux.org
  spotify
cd Programs/
git clone https://aur.archlinx.org/spotify.git
cd spotify/
ls
  PKGBUILD
less PKGBUILD
makepkg -si

yaourt
git clone https://aur.archlinux.org/package-query.git
cd package-query
makepkg si
cd ..
git clone https://aur.archlinux.org/yaourt.git
cd yaourt
makepkg -si
cd ..


yaourt -h


aurman
git clone https://aur.archlinux.org/aurman.git
cd aurman/
makepkg -si
  error: one or more pgp signatures could not be verified!
gpg --recv-keys 465022E743D71E39
makepkg -si

aurman -Ss fantasque
aurman -S otf-fantasque-sans-mono
aurman -Su
```

## Getting Started with Arch Linux 07 - The Arch User Repository (AUR) - YouTube d

```txt
pacman -Ss chrome
  no chrome

https://aur.archlinux.org
  package search: google chrome
    google-chrome
      download snapshot

pwd
tar -xvf google-chrome.tar.gz
cd google-chrome
ls
cat PKGBUILD
makepkg -s
ls -l
  google-chrome-73.pkg.tar.xz
sudo pacman -U google-chrome-73.pkg.tar.xz
rm -rf google-chrome*


sudo pacman -S git
which git
git clone https://aur.archlinux.org/yay.git
cd yay/
ls
  PKGBUILD
makepkg -s
ls
  yay-9.2.0-1.pkg.tar.xz
sudo pacman -U yay-9.2.0-1.pkg.tar.xz
which yay

yay minecraft
3
```

