# https://www.learnlinux.tv/setting-up-simple-samba-file-shares/
```
sudo apt install wsdd
sudo apt install samba
sudo systemctl status smbd
sudo systemctl stop smbd
sudo mv /etc/samba/smb.conf /etc/samba/smb.conf.original
```
```
[global]
server string = File Server
workgroup = WORKGROUP
security = user
map to guest = Never
name resolve order = bcast host
include = /etc/samba/shares.conf
```
```
[Public]
path = /home/admin-user/Public
create mask = 0640
force create mode = 0640
directory mask = 0750
force directory mode = 0750
public = no
writable = yes
browseable = yes
```
```
sudo systemctl start smbd
sudo smbpasswd -a admin-user
sudo systemctl status smbd
```
