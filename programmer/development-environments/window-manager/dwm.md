# dwm

## [10] _ DWM Getting Started - YouTube d

```txt
setfont ter-128n
sudo pacman -Syy
sudo pacman -S xorg-server xorg-xinit xorg-xrandr xorg-xsetroot chromium nitrogen picom

cp /etc/X11/xinit/xinitrc .xinitrc
ls -a
  .xinitrc
vim .xinitrc
  bottom remove 5 lines = twm to login

  # Keyboard Layout
  setxkbmap ch &

  # Display Resolution
  xrandr --output Virtual-1 --mode 1920x1080 &

  # Compositor
  picom -f &

  # Execute DWM
  exec dwm


sudo pacman -S wget
wget https://dl.suckless.org/dwm/dwm-6.2.tar.gz
ls
  dwm-6.2.tar.gz
tar -xzvf dwm-6.2.tar.gz
ls
  dwm-6.2
cd dwm-6.2
ls
sudo make clean install

wget https://dl.suckless.org/st/st-0.8.3.tar.gz
ls
tar -xzvf st-0.8.3.tar.gz
cd
sudo make clean install


startx
alt + shift + enter = terminal
alt + shift + c     = close

wget https://dl.suckless.org/tools/dmenu-4.9.tar.gz
tar -xzvf dmenu
cd dmenu-4.9
sudo make clean install

alt + shift + q = restart
startx
alt + p = menu
alt + p, chromium, enter
  japan 4k wallpaper
alt + p, nitrogen, enter
  preferences, add, /home/name/Downloads, ok, click an image, zoomed fill, apply


vim .xinitrc
  # Wallpaper
  nitrogen --restore &

  # Execute DWM
  exec dwm

alt + shift + q = quit dwm
startx
alt + 2 = 2
alt + 1 = 1
  terminal1
    alt + shift + 2 = move to workspace 2
    alt + shift + 1 = move to workspace 1
mod + l = resize
mod + h = resize


vim config.def.h
  #define MODKEY Mod1Mask = change to 1 to 4
  #define MODKEY Mod4Mask
alt + shift + q = quit dwm
startx
cd dwm-6.2
sudo cp config.def.h config.h
sudo make clean install
alt + shift + q = quit dwm
startx
shift + enter = terminal
```

## [10a] _ DWM Patching & Start Loop - YouTube d

```txt
vim .xinitrc
  # Loop
  while true; do
    dwm >/dev/null 2>&1
  done

  # Execute DWM
  exec dwm

alt + shift + q = exit dwm
startx
alt + shift + q = exit dwm and open automatically


mod + p, chromium
  dwm patches
  dwm.suckless.org/patches/fullgaps/
    save as, /home/name/dwm-6.2, dwm-fullgaps-6.2.diff, save
cd dwm-6.2
ls
  dwm-fullgaps-6.2.diff
patch < dwm-fullgaps-6.2.diff
sudo cp config.def.h config.h
sudo make clean install


vim config.def.h
patch -R < dwm-fullgaps-6.2.diff           = remove patch
sudo cp config.def.h config.h
sudo make clean install
alt + shift + q = exit dwm and open automatically
cd dwm-6.2
rm dwm-fullgaps-6.2.diff


APPLY MANUAL PATCH IF THE PATCH FAIL
  dwm.suckless.org/patches/fullgaps/
    save as, /home/name/dwm-6.2, dwm-fullgaps-12312312-12312312.diff, save
patch < dwm-fullgaps.diff
  failed dwm.c.rej
vim dwm.c.rej
  :tabnew
  :e dwm.c
    copy the lines that has + at dwm.c.rej
sudo cp config.def.h config.h
sudo make clean install
alt + shift + q = exit dwm and open automatically


https://dwm.suckless.org/patches/alpha/
  save as, dwm-alpha-20180613-b69c870.diff, save
patch < dwm-alpha-20180613-b69c870.diff
sudo cp config.def.h config.h
sudo make clean install
alt + shift + q = exit dwm and open automatically

sudo vim /etc/xdg/picom.conf
  # vsync = true;            = not supported in the vm
reboot
login
startx
```

## [10b] _ DWM Git Install & Patching - YouTube d

```txt
sudo pacman -S xorg-server xorg-xinit xorg-xrandr xorg-xsetroot chromium
cp /etc/X11/xinit/xinitrc .xinitrc
vim .xinitrc
  bottom remove 5 lines = twm to login

  # Keyboard
  setxkbmap ch &

  # Display
  xrandr --output Virtual-1 --mode 1920x1080 &

  # Loop
  while true; do
    dwm >/dev/null 2>&1
  done

  # DWM
  exec dwm



git clone https://git.suckless.org/dwm
git clone https://git.suckless.org/st
git clone https://git.suckless.org/dmenu
cd dwm/
make && sudo make clean install
cd st/
make && sudo make clean install
cd dmenu/
make && sudo make clean install

cd dwm/
startx
git branch
git config user.email "name@gmail.com"
git config user.name "name"
make clean && rm -f config.h && git reset --hard origin/master

git branch config
git branch
  config
  master
git checkout config
vim config.def.h
  #define MODKEY Mod4Mask
git add config.def.h
git commit -m config
git checkout master
git merge config -m config
make && sudo make clean install
alt + shift + q = restart dwm
shift + enter = terminal


git branch
  master
make clean && rm -f config.h && git reset --hard origin/master
git branch fullgaps
chromium
  save as, dwm-fullgaps-6.2.diff, save
git checkout fullgaps
patch <  ~/Downloads/dwm-fullgaps-6.2.diff
vim dwm.c.rej
  copy lines with + and paste in dwm.c
git add dwm.c config.def.h
git commit -m fullgaps
git checkout master
git merge config -m config
git merge fullgaps -m fullgaps
make && sudo make clean install
```

## [10c] _ DWM Status Bar Customization - YouTube

```txt
```
