# Bdbd

1) Update the server, install taskel then install ubuntu desktop:

sudo apt-get update && sudo apt-get upgrade -y
sudo apt install tasksel
sudo tasksel install ubuntu-desktop


2) install and enable remote desktop with xrdp

sudo apt install xrdp -y
sudo systemctl enable --now xrdp

3) Add the port 3389 to the iptables and save

sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 3389 -j ACCEPT
sudo netfilter-persistent save

4) create a user for xdrp 

sudo adduser ideaspot
sudo usermod -G xrdp ideaspot

5) reboot server

sudo reboot
