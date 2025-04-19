# https://www.learnlinux.tv/setting-up-simple-samba-file-shares/

sudo apt install wsdd

sudo apt install samba

sudo systemctl status smbd

sudo systemctl stop smbd

sudo mv /etc/samba/smb.conf /etc/samba/smb.conf.original


[global]
server string = File Server
workgroup = LLTV
security = user
map to guest = Never
name resolve order = bcast host
include = /etc/samba/shares.conf
