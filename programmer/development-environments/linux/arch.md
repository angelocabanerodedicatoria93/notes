# arch

```txt
requirements
  ethernet
  usb drive
  linux knowledge

archlinux.org
```

```sh
lsblk
  sda
  sr0
lsblk
  sda
  sdb (usb)
    sdb1
    sdb2

sudo su
man dd
dd if=Downloads/archlinux-2018.03.01-x86_64.iso of=/dev/sdb status="progress"
lsblk
  sdb
    sdb1 = 551m
    sdb2 =  64m

f2, f10, delete
  boot usb drive

packer arch linux scripts

lsblk
  sdb
    sdb1 = 298.1g

ls /sys/firmware/efi/efivars
  no such file or directory = traditional bios not uefi
ping lukesmith.xyz
wifi-menu
timedatectl set-ntp true
lsblk
fdisk /dev/sdb
  m, p, d, p,
  n, (1) enter, enter, +200M, y, p,          Boot Partition
  n, p, 2, enter, +12G, p,                   Swap Partition
  n, p, 3, enter, +25G, y                    Root Partition = /
  n, p, enter, enter, y                      Home Partition
  p
    /dev/sdb1    200M
    /dev/sdb2     12G
    /dev/sdb3     25G
    /dev/sdb4  260.9G
  w
lsblk
  sdb
    sddb1
    sddb2
    sddb3
    sddb4
mkfs.ext4 /dev/sdb1
mkfs.ext4 /dev/sdb3
mkfs.ext4 /dev/sdb4
lsblk
mkswap /dev/sdb2
swapon /dev/sdb2
mount /dev/sdb3 /mnt
ls /mnt
  lost+found
lsblk
mkdir /mnt/home
ls /mnt
  home, lost+found
mkdir /mnt/boot
ls /mnt
  boot, home, lost+found
lsblk
mount /dev/sdb1 /mnt/boot
mount /dev/sdb4 /mnt/home
lsblk
  sdb
    sdb1   200M /mnt/boot
    sdb2    12G [SWAP]
    sdb3    25G /mnt
    sdb4 260.9G /mnt/home
pacstrap -h
pacstrap /mnt base base-devel vim

vim /etc/fstab

genfstab
genfstab /mnt
genfstab -U /mnt
genfstab -U /mnt >> /mnt/etc/fstab
vim /mnt/etc/fstab
  /     ext4
  /boot ext4
  /home ext4
  none  swap
arch-chroot /mnt
ls
  /
vim /etc/fstab
pacman -S networkmanager
systemctl enable NetworkManager
pacman -S grub
lsblk
  sdb    298.1G
    sdb1   200M /boot
    sdb2    12G [SWAP]
    sdb3    25G /
    sdb4 260.9G /home
grub-install --target=i386-pc /dev/sdb
grub-mkconfig -o /boot/grub/grub.cfg
passwd
vim /etc/locale.gen
  /en_US
    en_US.UTF-8 UTF-8  = uncomment
    en_US ISO-8859-1   = uncomment
  wq
locale-gen
vim /etc/locale.conf
  LANG=en-US.UTF-8
  :x = save
ls /usr/share/zoneinfo/
ls /etc/
ls /etc/localtime
ln -sf /usr/share/zoneinfo/
ln -sf /usr/share/zoneinfo/America/Phoenix /etc/localtime

vim /etc/hostname
  archinstall
  :x = save
exit
lsblk
  sdb    298.1G
    sdb1   200M /boot
    sdb2    12G [SWAP]
    sdb3    25G /
    sdb4 260.9G /home
umount -R /mnt
lsblk
  sdb    298.1G
    sdb1   200M
    sdb2    12G [SWAP]
    sdb3    25G
    sdb4 260.9G
reboot

root
password

d
Full Arch Linux Install (SAVAGE Edition!) - YouTube
```



```sh
archlinux.org
  download
    bittorrent download
  wiki
    installation guide

virtual box
  new
    Arch Linux, next, 4G ram next, create a virtual hard disk now, create, vdi, next, dynamically allocated, 15GB, create
  Arch Linux
    settings
      system
        processor, processors = 2
      display
        video memory = 128mb, graphics controller = vboxvga, acceleration = enable 3d acceleration
      storage
        controller: IDE, Adds optical drive., choose disk, archlinux.iso, choose
      user interface
        uncheck all to hide
  start

Boot Arch Linux (x86_64)
ping google.com
timedatectl set-ntp true
timedatectl status
lsblk
  sda 15G
cfdisk
  dos
    new = enter, 13G, primary, bootable = enter, boot = *
    Free space, new, 2G, primary, Type, 82 Linux swap / Solaris, enter
    write, enter, yes, quit = enter
mkfs.ext4 /dev/sda1
lsblk
  sda
    sda1 13G
    sda2  2G
mkswap /dev/sda2
swapon /dev/sda2
mount /dev/sda1 /mnt
nano /etc/pacman.d/mirrorlist
  ## United States
  Server = http://arch
    don't delete mirrorlist that is close to you
  ctrl + x = save, y

pacstrap /mnt base
genfstab -U /mnt >> /mnt/etc/fstab
arch-chroot /mnt

ln -sf /usr/share/zoneinfo/America/Chicago /etc/localtime
ls /usr/share/zoneinfo
ls /usr/share/zoneinfo/America
hwclock --systohc
locale-gen
nano /etc/locale.conf
  LANG=en_US.UTF-8
nano /etc/hostname
  dt
nano /etc/hosts
  127.0.0.1  localhost
  ::1        localhost
  127.0.1.1  dt.localdomain dt
passwd

archlinux.org
  wiki
    Network configuration

systemctl enable dhcpcd

archlinux.org
  wiki
    users and groups

useradd -m derek
passwd derek
whereis sudo = nothing is return
pacman -S sudo
usermod -aG wheel,audio,video,optical,storage derek
groups derek
pacman -S vim
visudo
  %wheel ALL=(ALL) ALL
  :wq = save and quit

archlinux.org
  wiki
    arch boot process

pacman -S grub
grub-install /dev/sda
grub-mkconfig -o /boot/grub/grub.cfg
exit
shutdown now

virtual box
  settings
    storage
      controller: IDE = archlinux-2019 = remove, ok
  start

dt login: derek
password

ping google.com
sudo pacman -S xorg


d
Arch Linux Installation Guide (2019) - YouTube
```

```sh
f12
boot menu
  usb hdd, enter
arch linux archiso x86_64 uefi cd

ip addr show
wifi-menu
  choose wifi network, password
ip a
ping -c 5 www.learnlinux.tv

nano /etc/pacman.d/mirrorlist
  choose mirrors that is near to you
pacman -Syyy


fdisk -l
fdisk -l :more
lsblk
  nvme0n1
    nvme0n1p1
    nvme0n1p2
fdisk /dev/nvme0n1
  p, g, p
  n, enter, enter, +500M, y, t, 1,       efi system
  n, enter, enter,  +30G, y              /
  n, enter, enter, enter                 home
  p
    /dev/nvme0n1p1   500M efi system
    /dev/nvme0n1p2    30G linux filesystem
    /dev/nvme0n1p3 446.5G linux filesystem
  w
lsblk
  nvme0n1
    nvme0n1p1   500M
    nvme0n1p2    30G
    nvme0n1p3 446.5G

mkfs.fat -F32 /dev/nvme0n1p1
mkfs.ext4 /dev/nvme0n1p2
mkfs.ext4 /dev/nvme0n1p3

lsblk
mount /dev/nvme0n1p2 /mnt
mkdir /mnt/home
mount /dev/nvme0n1p3 /mnt/home
mount
df -h
  /dev/nvme0n1p2 /mnt
  /dev/nvme0n1p3 /mnt/home

mkdir /mnt/etc
genfstab -U -p /mnt >> /mnt/etc/fstab
cat /mnt/etc/fstab
  /dev/nvme0n1p2      /     ext4
  /dev/nvme0n1p3      /home ext4

pacstrap -i /mnt base
arch-chroot /mnt
pacman -S linux linux-headers linux-lts linux-lts-headers
  enter, enter
pacman -S nano
pacman -S openssh base-devel
systemctl enable sshd
pacman -S networkmanager wpa_supplicant wireless_tools netctl
  enter
pacman -S dialog
systemctl enable NetworkManager
mkinitcpio -p linux
mkinitcpio -p linux-lts

nano /etc/locale.gen
  en_US.UTF-8 UTF-8
locale-gen

passwd
useradd -m -g users -G wheel jay
passwd jay

which sudo
  /usr/bin/sudo
  if error
  pacman -S sudo
EDITOR=nano visudo
  %wheel ALL=(ALL) ALL

pacman -S grub efibootmgr dosfstools os-prober mtools
mkdir /boot/EFI
mount /dev/nvme0n1p1 /boot/EFI
grub-install --target=x86_64-efi --bootloader-id=grub_uefi --recheck
mkdir /boot/grub/locale
cp /usr/share/locale/en\@quot/LC_MESSAGES/grub.mo /boot/grub/locale/en.mo
grub-mkconfig -o /boot/grub/grub.cfg

fallocate -l 2G /swapfile
chmod 600 /swapfile
mkswap /swapfile
cp /etc/fstab /etc/fstab.bak
echo '/swapfile none swap sw 0 0' : tee -a /etc/fstab
cat /etc/fstab
  /dev/nvme0n1p2  /
  /dev/nvme0n1p3  /home

pacman -S intel-ucode
pacman -S xorg-server
pacman -S mesa

pacman -S nvidia nvidia-utils nvidia-lts
pacman -S virtualbox-guest-utils xf86-video-vmware

exit
umount -a
poweroff

remove the flash drive
turn on and login

d
Arch Linux Full Installation Walkthrough - YouTube
```







```sh

download iso file and iso.sig

gpg --keyserver-options auto-key-retrieve --verify Downloads/archlinux-2020.04.01-x86_64.iso.sig
  good signature

dd bs=4M if=/path/to/archlinux.iso of=/dev/sdx status=progress && sync
sudo reboot now

Arch Linux archiso x86_64 UEFI USB

ls /sys/firmware/efi/efivars/
ping -c 3 archlinux.org
ip link
wifi-menu
timedatectl set-ntp true
date

lsblk
  sda
cfdisk /dev/sda
  gpt
    partition size = 512M        /efi
                   =  20G        /
                   = 9.5G        /home
    write, yes, quit
lsblk
  sda
    sda1
    sda2
    sda3

mkfs.fat -F32 /dev/sda1
mkfs.ext4 /dev/sda2
mkfs.ext4 /dev/sda3

mount /dev/sda2 /mnt
mkdir /mnt/home
mount /dev/sda3 /mnt/home
lsblk
  sda1
  sda2    /mnt
  sda3    /mnt/home

pacstrap /mnt base linux linux-firmware

genfstab -U /mnt >> /mnt/etc/fstab
cat /mnt/etc/fstab
  /dev/sda2  /
  /dev/sda3  /home

arch-chroot /mnt /bin/bash
ln -sf /usr/share/zoneinfo/
ln -sf /usr/share/zoneinfo/Europe/Stockholm /etc/localtime

hwclock --systohc --utc
date

nano /etc/locale.gen
pacman -S nano
nano /etc/locale.gen
  en_US.UTF-8 UTF-8

echo LANG=en_US.UTF-8 > /etc/locale.conf
cat /etc/locale.conf

echo archPC > /etc/hostname
nano /etc/hosts
  127.0.1.1 localhost.localdomain archPC

pacman -S networkmanager
systemctl enable NetworkManager

passwd

pacman -S grub efibootmgr
mkdir /boot/efi
mount /dev/sda1 /boot/efi/
lsblk
  sda
    sda1 /boot/efi
    sda2 /
    sda3 /home

grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=GRUB --removable
grub-mkconfig -o /boot/grub/grub.cfg
exit
umount -R /mnt
reboot

Arch Linux, enter
login = root

useradd -m -g users -G wheel -s /bin/bash alu
passwd alu
EDITOR=nano visudo

pacman -S sudo
EDITOR=nano visudo
  %wheel ALL=(ALL) ALL
exit
login = alu

sudo fallocate -l 3G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
free -m
  swap 3071
sudo nano /etc/fstab
  # swapfile
  /swapfile  none swap sw 0 0
cat /etc/fstab

sudo pacman -S pulseaudio pulseaudio-alsa xorg xorg-xinit xorg-server xfce4 lightdm lightdm-gtk-greeter bash-completion

echo "exec startxfce4" > ~/.xinitrc
sudo systemctl enable lightdm
startx


d
Arch Linux Installation (2020) - YouTube
```

## Arch Linux on a USB Stick - YouTube

```sh
localectl list-keymaps | grep CH
  de_CH-latin1
loadkeys de_CH-latin1
ip a
iwctl
device list
station wlan0 scan
station wlan0 get-networks
station wlan0 connect name
exit
```

```sh
pacman -Syy reflector
reflector -c Switzerland -a 6 --sort rate --save /etc/pacman.d/mirrorlist
pacman -Syy
```

```sh
lsblk
  sdb
gdisk /dev/sdb
n, enter, enter, +200M             /efi
ef00
n, enter, enter, enter, enter      /
w, Yes
lsblk
  sdb
    sdb1
    sdb2
mkfs.fat -F32 /dev/sdb1
mkfs.ext4 -O "^has_journal" /dev/sdb2
```

##  Arch Linux July 2020 ISO Wi-Fi with iwd - YouTube d

```sh
iwctl
device list
  wlan0
station wlan0 scan
station wlan0 get-networks
station wlan0 connect name
exit
ip a
```

## Install Arch Linux Walkthrough [NEW 2020] - YouTube

```txt
https://www.chrisatmachine.com/Linux/01-Arch-Linux-Install-UEFI/
https://wiki.archlinux.org/index.php/Installation_guide
https://balena.io/etcher/

arch linux archiso x86_64 UEFI CD
ls /sys/firmware/efi/efivars
ping archlinux.org
ip link
wifi-menu
```

```sh
timedatectl set-ntp true
fdisk -l
  /dev/vda1
  /dev/vda2
  /dev/vda3
fdisk /dev/vda
m, g
n, enter, enter, +512M, yes, t, 1                 /boot
n, enter, enter, +26G, yes, t, enter, l, 24       /root
n, enter, enter, enter, yes, t, enter, l, 28      /home
w
```

```sh
mkfs.vfat /dev/vda1
mkfs.ext4 /dev/vda2
mkfs.ext4 /dev/vda3

mount /dev/vda2 /mnt
mkdir /mnt/boot
mkdir /mnt/home
mount /dev/vda1 /mnt/boot
mount /dev/vda3 /mnt/home
df
  /dev/vda2         /mnt
  /dev/vda1         /mnt/boot
  /dev/vda3         /mnt/home


pacstrap /mnt base base-devel linux linux-firmware vim dhcpcd
genfstab -U /mnt >> /mnt/etc/fstab
cat /mnt/etc/fstab
  /
  /boot
  /home
arch-chroot /mnt


fallocate -l 6GB /swapfile
chmod 600 /swapfile
mkswap /swapfile
swapon /swapfile
vim /etc/fstab
  /swapfile    none  swap  default 0 0


ln -sf /usr/share/zoneinfo/America/New_York /etc/localtime
hwclock --systohc
vim /etc/locale.gen
  en_US.UTF-8 UTF-8
locale
locale-gen

vim /etc/locale.conf
  LANG=en_US.UTF-8
vim /etc/hostname
  vm
vim /etc/hosts
  127.0.0.1 localhost
  ::1       localhost
  127.0.1.1 vm.localdomain vm


passwd
pacman -S grub efibootmgr os-prober
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB
grub-mkconfig -o /boot/grub/grub.cfg
exit


umount -a
reboot
```

## Arch Linux Installation (2020) _ Full Guide - YouTube

```
```
```
```
```
```
```
```
```

