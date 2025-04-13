sudo apt install xrdp
sudo systemctl start xrdp
sudo systemctl enable xrdp
sudo systemctl status xrdp
sudo adduser xrdp ssl-cert
sudo systemctl restart xrdp
sudo systemctl status xrdp

sudo ufw status
sudo ufw allow 3389/tcp
sudo ufw status
