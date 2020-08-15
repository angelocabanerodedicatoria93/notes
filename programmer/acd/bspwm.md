# bspwm

## Arch Linux BSPWM - Part 1 - YouTube

```txt
setfont ter-132n
sudo pacman -S xf86-video-qxl xorg xorg-xinit bspwm sxhkd dmenu nitrogen picom xfce4-terminal chromium arandr
mkdir .config/bspwm
mkdir .config/sxhkd
cp /usr/share/doc/bspwm/examples/bspwmrc .config/bspwm/
cp /usr/share/doc/bspwm/examples/sxhkdrc .config/sxhkd/
```

```txt
vim .config/sxhkd/sxhkdrc
  super + Return
          xfce4-terminal
```

```txt
cp /etc/X11/xinit/xinitrc .xinitrc
vim .xinitrc
  twm &
  xclock -geometry 50x50-1+1 &
  xterm -geometry 80x50+494+51 &
  exec xterm -geometry 80x66+0+0 -name login             = remove

  setxkbmap ch &
  picom -f &
  exec bspwm
```

```txt
sudo vim /etc/xdg/picom.conf
  # vsync = true;
startx
```


```txt
super + enter = terminal
super + space = dmenu and type arandr
arandr
  outputs
    virtual-1
      resolution = 1920x1080
        apply, save = display
super + w = close
chmod +x .screenlayout/display.sh
```

```txt
vim .xinitrc

  setxkbmap ch &
  $HOME/.screenlayout/display.sh
  picom -f &
  exec bspwm
```


```
mod + alt + q = exit
startx
mod + enter = terminal

```


```txt
vim .xinitrc
  setxkbmap ch &
  $HOME/.screenlayout/display.sh
  xsetroot -cursor_name left_ptr
  picom -f &
  exec bspwm
```

```txt
mod + alt + q = exit
startx
```


```
super + space = chromium
japan 4k wallpapers
super + space = nitrogen
preferences, add, Pictures, zoomed fill, apply
super + w = close nitrogen
```

```txt
vim .xinitrc
  setxkbmap ch &
  $HOME/.screenlayout/display.sh
  nitorgen --restore &
  xsetroot -cursor_name left_ptr
  picom -f &
  exec bspwm
```

```
super + alt + q = exit window manager
startx
```


```
```
```
```
```
```
```
```
```
```
```
```
```
```
```
```
```
```
