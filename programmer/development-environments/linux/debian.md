# Debian

## Debian 10 Installation Guide - YouTube

```txt
Which ISO to donwload?
How to use the partition manager?
What if your Wi-Fi doesn't work?
How to get a sudo access for your user?
How to fix the repository cdrom error
```





```txt
small installation image
complete installation image
```





```txt
sudo dd bs=4M if=Downloads/debian-10.0.0-amd64-DVD-1.iso of=/dev/sdc status=progress && sync
boot to usb
graphical install
english
debian10
```


```txt
manual
Ext4 journaling file system
Format the partition: no, keep existing data, enter
Format the partition: yes, format it
Mount point: /
Label: debian
Erase data on this partition, YES
Done setting up the partition
```

```txt
EFI system p
Finish partitioning and write changes to disk
```

```txt
sudo fallocate  -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo nano /etc/fstab
  /swapfile swap swap dafaults 0 0
sudo reboot
free -h
  mem
  swap: 2.0Gi
```


```txt
sudo apt update
  E: the repository 'cdrom
sudo nano /etc/apt/source.list
  # deb cdrom:[Debian GNU/Linux 10.0.0
sudo apt update
```







## 30 things to do after installing Debian 10 - YouTube

```sh
software & updates
  other software
    cdrom = uncheck
  debian software
    download from
      other
        select best server
        choose server
```

```sh
sudo apt update
  404 Not Found
  E: The repository 'http://debian.mirror
sudo nano /etc/apt/sources.list
  deb http://debian.mirror.su.se/debian/ buster/updates main
  deb-src http://debian.mirror.su.se/debian buster/updates main
  change to
  deb http://security.debian.org/debian-security buster/updates main
  deb-src http://security.debian.org/debian-security buster/updates main
sudo apt update
```



```sh
software & updates
  debian software
    dfsg-compatible software with non-free dependencies (contrib) = uncheck
    non-dfsg-compatible software (non-free)                       = uncheck
```

```sh
ps -e | grep X
  Xwayland
Sign in
  system x11 default
ps -e | grep X
  Xorg
```


```sh
tweaks
  window titlebars
    minimize = on
```


```sh
synaptic package manager
sudo apt install synaptic
```

```sh
synaptic
  -microcode
    intel-microcode = mark for installation
  apply
```


```sh
sudo apt install build-essential dkms linux-headers-$(uname -r)
```

```sh
sudo apt -y install nvidia-detect
sudo nvidia-detect
sudo apt install nvidia-driver
```


```sh
sudo apt install ubuntu-restricted-extra
  error
sudo apt install ttf-mscorefonts-installer rar unrar libavcodec-extra gstreamer1.0-libav gstreamer1.0-plugins-ugly gstreamer1.0-vaapi
```



```sh
sudo apt install ufw
sudo ufw enable
sudo ufw status verbose
sudo ufw app list
sudo ufw allow ssh
sudo ufw allow 22/tcp
sudo ufw status numbered
  1 22/tcp
  2 22/tcp (v6)
sudo ufw delete 1
```

```sh
grsync
luckybackup
```


```sh
cat /proc/sys/vm/swappiness
  60
sudo nano /etc/sysctl.conf
  vm.swappiness = 10
sudo reboot
cat /proc/sys/vm/swappiness
  10
```


```sh
sudo nano /etc/default/grub
  GRUB_TIMEOUT=0
sudo update-grub
sudo reboot
```


```sh
disks
drive settings
wirte cache = enable write cache
```


```sh
sudo apt install tlp
sudo systemctl status tlp
```





## Debian 10 Buster Release and Install - YouTube

```sh
sudo dpkg --configure -a
sudo apt clean
sudo apt autoremove
```

```sh

getting debian
  try deban live before installing
    amd64
      /images/unoffical/non-free/images-including-firmware/
        10.0.0-live+nonfree/
          amd64/
            iso-hybrid/
              debian-live-10.0.0-amd64-kde+nonfree.iso

boot this on usb
```



```sh
graphical debian installer
hostname = debian10
domainname = blank
set up users and passwords = blank
set up users and passwords
  full name for the new user = titus
  password = titus
```


```sh
partition disks
  guided - use entire disk, continue, continue, finish partitioning = continue, yes
configure the package manager
  yes
install the grub boot loader on a hard disk
  /dev/sda (ata-VBOX_HARDDISK_VB043)
reboot
```


```sh
alternatives...
  application menu = switch

system settings
  startup and shutdown
    login screen (SDDM)
      get new theme
        mcmojave sddm

  workspace theme
    get new looks
      arc kde
        arc dark, apply

configure desktop
  debian wallpaper
reboot
d
```


## How to install Debian 10 Buster (Live Media Method) Installation Walkthrough and Tutorial - YouTube

```sh
debian.org
  live
    dvd/usb
      amd64
        debian-live-10.0.0-amd64-gnome+nonfree.iso
create a bootable media
f2, f12, f7
  usb

debian gnu/linux live
install debian
partitions
  samsung ssd
```
