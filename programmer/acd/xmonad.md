# xmonad

## XmonadBeginner Guide part 1 - YouTube

```txt
sudo pacman -S xmonad xmonad-contrib xmobar stalonetray
```

## [11] _ Xmonad Basic Install - YouTube d

```txt
setfont ter-128n

sudo pacman -Syy xorg lightdm lightdm-gtk-greeter xmonad xmonad-contrib xmobar dmenu picom nitrogen chromium terminator
sudo systemctl enable lightdm

sudo vim /etc/lightdm/lightdm.conf
  display-setup-script=xrandr --output Virtual-1 --mode 1920x1080           = for vm
sudo vim /etc/xdg/picom.conf
  # vsync = true;                                                           = for vm



vim .xprofile

mkdir .xmonad
cd .xmonad/
vim xmonad.hs
reboot



mod + shift + enter = terminal
terminal
  preferences
    profiles
      general
        use the system fixed widht font = uncheck
        font:                           = source code pro
        size:                           = 16
        show titlebar                   = uncheck
      scrolling
        scrollbar is:                   = disabled
      background
        transparent background
        0.90

mod + shift + enter = terminal

mod + p             = dmenu
  chromium
    japan 4k wallpaper
mod + p             = dmenu
  nitrogen
    preferences
      add
        /home/name/Downloads = select, ok
    select, zoomed fill, apply

mod + shift + enter = terminal
mod + p             = dmenu
  chromium
mod + shift + 2 = chromium move to workspace 2
mod + 2 = go to workspace 2
mod + shift + c = close
mod + shift + q = quit xmonad


mod + shift + enter = terminal
mod + shift + enter = terminal
mod + k = go to right
mod + j = go to left
mod + l = increase size
mod + h = decrease size
```

## [11a] _ Xmonad & Xmobar customizaion - YouTube d

```
vim .xmonad/xmonad.hs
install pcmanfm


https://ermannoferrari.net/xmonad-config-file
https://ermannoferrari.net/xmobar-config-file

mv .xmonad/xmonad.hs .xmonad/xmonad.hs.bak
cp Downloads/xmonad.hs .xmonad/
cd .xmonad
mod + q = reload xmonad

cp Downloads/xmobar .xmobarrc
vim .xmobarrc
mod + shift + q = reload xmonad
  text is white
vim .xmobarrc

chromium
  basel airport ICAO


sudo pacman -S ttf-font-awesome alsa-utils pamixer
vim .xmonad/xmonad.hs
chromium
  font awesome
  https://fontawesome.com/cheatsheet
    terminal
    microchip
xmonad --recompile
fc-list | grep Awesome
mod + q = quit xmonad
chromium
  https://fontawesome.com/cheatsheet
    microchip
reboot


mod + mouse left click + move your mouse = floating window
mod + space = mirror tall
mod + space = full
mod + space = tall
```

## Getting Started With Xmonad - YouTube d

```txt
sudo apt install xmonad xmonad-contrib
  error xmonad-contrib
apt search xmonad-contrib
sudo apt install xmonad libghc-xmonad-contrib-dev xterm dmenu
logout
xmonad

mod + shift + enter = terminal
mod + shift + c = close
mod + p = dmenu
  firefox
    xmonad config archive
       download the latest darcs template xmonad.hs
mv xmonad.hs ~/.xmonad/xmonad.hs
vim xmonad.hs

alt + q = restart xmonad
super + shift + enter = terminal
super + j and k  = switch
super + tab = change focus
super + space = change layout

sudo apt install compton nitrogen
super + q = restart xmonad
  variable not in scope: spawnOnce
mod + p = dmenu
  firefox
    xmonad spawnonce
    haskell.org
super + q = restart xmonad
super + p = dmenu
  nitrogen
    preferences
      add
        /usr/share/bakgrounds
        select
        ok
    apply
    scaled

super + p
  gnome-terminal
vim .xmonad/xmonad.hs

FOR VM
xrandr
xrandr -s 1920x1080


sudo apt install xmobar
sudo find / -iname xmombar
  /usr/share/doc/xmobar
cd /usr/share/doc/xmobar
cd examples/
mkdir /home/dt/.config/xmobar/
cp xmobar.config /home/dt/.config/xmobar/xmobarrc
vim xmobarrc
vim xmonad.hs


super + 1 = workspace 1

firefox
  xmonad managdocks

super + q = restart, xmobar display
killall xmobar
super + q

xdotool

monocle
master
stack
```

## Recently Left i3 For Dwm If so, keep moving...to Xmonad! d

## XmonadBeginner Guide part 1 - YouTube d

```txt

https://github.com/boylemic/configs/tree/master/xmonad

sudo pacman -S xmonad xmonad-contrib xmobar stalonetray
vim .xinitrc
vim .stalonetrayrc

mkdir ~/.xmonad
cd ~/.xmonad
gedit xmonad.hs
```

## Xmonad TreeSelect Is A Unique Menu System - YouTube d

## Hacking On Xmonad - ManageHooks, Prompts and Hoogle - YouTube d

## Xmonad Is The Super Hackable Tiling Window Manager - YouTube

## Hacking on Xmonad - GridSelect, ToggleStruts, ToggleBorders - YouTube

```txt
xmonad.hs
  import XMonad.Hooks.ManageDocks (avoidStruts, docsStartupHook, manageDocks, ToggleStruts(..))
  , ("M-S-<Space>", sendMessage ToggleStruts)       --Toggles struts

  import XMonad.Layout.NoBorders
  , ("M-S-n", sendMessage $ Toggle NOBORDERS)       --Toggles noborder
```
