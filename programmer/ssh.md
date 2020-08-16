# ssh

## Learn SSH In 6 Minutes - Beginners Guide to SSH Tutorial - YouTube d

```txt
ssh
ssh james@142.93.58.60
ssh james@server.juniordevelopercentral.com

ls .ssh
  id_rsa
  id_rsa.pub

ssh-keygen
ssh-copy-id root@server.juniordevelopercentral.com

ssh root@server.juniordevelopercentral.com

scp index.html james@server.juniordevelopercentral.com:/var/www/html

chrome
  server.juniordevelopercentral.com
    Hello World!
```

## How to install and use SSH on Linux - YouTube d

```txt
sudo apt install openssh-client

REMOTE COMPUTER
sudo apt install openssh-server
sudo systemctl status ssh
sudo systemctl start ssh
ip a
sudo lsof -i -P -n | grep LISTEN


sudo ufw allow 22
sudo ufw status


ssh alu@94.237.40.210
password
ping AverageLinuxUser.com



filezilla
  site Manager
    new site
    protocol: sftp - ssh file transfer protocol
    host:     94.237.40.210
    port:     22
    user:     alu
    passowrd:
    connect


ssh -X alu@94.237.40.210
firefox-esr


scp /home/alu/file.txt alu@94.237.40.210:/home/alu/
scp alu@94.237.40.210:/home/alu/UpCloudFile.txt /home/alu/
```

## Linux Tutorial for Beginners - 15 - SSH Key Authentication - YouTube d

```txt
ssh-keygen -t rsa

ssh-copy-id root@45.55.248.198
ssh root@45.55.248.198
```

## How to use SSH Public Key authentication - YouTube d

```txt
upcloud.com
  promo code= alu25

ssh-keygen
ssh-keygen
  id_rsa_upcloud
ls .ssh
cat .ssh/id_rsa
cat .ssh/id_rsa.pub


ssh-copy-id -i ~/.ssh/id_rsa.pub alu@94.237.40.210
or
scp

cat ~/.ssh/id_rsa.pub | ssh alu@94.237.40.210 "cat >> ~/.ssh/authorized_keys"

LOCAL COMPUTER
cat .ssh/id_rsa.pub
  copy

REMOTE COMPUTER
vi .ssh/authorized_keys
  paste

ssh alu@94.237.40.210
  password
sudo vi /etc/ssh/sshd_config
  PasswordAuthentication no
sudo systemctl restart ssh
ssh alu@94.237.40.210


PASSWORD-LESS LOGIN
ssh-keygen
ssh-copy-id -i ~/.ssh/id_rsa.pub alu@94.237.42.124
ssh alu@94.237.42.124



SSH AUTHENTICATION AGENT
eval `ssh-agent -s`
ssh-add ~/.ssh/id_rsa
ssh alu@94.237.42.124
logout
```

