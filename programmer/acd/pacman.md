# pacman

## Using Pacman on Arch Linux Everything you need to know - YouTube d

```txt
man pacman
pacman -S                        sync
pacman -R
pacman -Q


sudo pacman -S emacs


sudo pacman -Syu                 sync and update all my programs
sudo pacman -Su                  update
sudo pacman -Syyu                double check
sudo pacman -Syyuw               download and manual install


pacman -Ss emacs                 search an app
pacman -Ss ^emacs


pacman -R vidir
sudo pacman -Rs vidir
sudo pacman -Rns vidir            uninstall an app


pacman -Q                         list of apps installed
pacman -Q | wc -l
pacman -Qe
pacman -Qe | wc -l
pacman -Qeq
pacman -Qn
pacman -Qm                        apps from aur
pacman -Qdt                       apps you don't need
pacman -Qs emacs


sudo vim /etc/pacman.conf
  #UseSyslog
  Color
  #TotalDownload
  CheckSpace
  #VerbosePkgLists
  ILoveCandy

  [core]
  Include = /etc/pacman.d/mirrorlist

  [extra]
  Include = /etc/pacman.d/mirrorlist

  [community]
  Include = /etc/pacman.d/mirrorlist



sudo vim /etc/pacman.d/mirrorlist
  ## United States
  Server = http://mirrors.aggregate.org/archlinux/$repo/os/$arch
server must close to you



man pacman



df -h
  3.9G  /dev
  3.9G  /run
   30G  /
  3.9G  /dev/shm
  3.9G  /sys/fs/cgroup
  3.9G  /tmp
  190M  /boot
  850G  /home
  790M  /run/user/1000



sudo pacman -Sc
df -h
```

## (24) The Pacman Package Manager in Arch Linux - YouTube d

```txt
su
exit
sudo pacman -Syu

sudo pacman -S guvcview            install package
sudo pacman -R guvcview            remove package
sudo pacman -Rs guvcview           remove package and dependencies



sudo pacman -Ss guvcview           search repository package
sudo pacman -Qs firefox            search for installed package



pacman -Qdt                        list of packages that are no longer needed
sudo pacman -Rns $(pacman -Qtdq)   remove packages



sudo pacman -Syu
sudo pacman -S name
sudo pacman -R name
sudo pacman -Rs name
sudo pacman -Ss name
sudo pacman -Qs name
pacman -Qdt
sudo pacman -Rns $(pacman -Qtdq)
man pacman
```
