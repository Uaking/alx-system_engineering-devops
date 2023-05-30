#!/usr/bin/env bash
# Installs firewall
# block all incoming except 22, 443, 80
# install ufw, support both IPv4 and IPv6, and ensure default values

sudo apt-get -y install ufw
sudo sed -i "s/IPV6=no/IPV6=yes/" /etc/default/ufw
sudo ufw default allow outgoing
sudo ufw default deny incoming

# configure
sudo ufw allow ssh
sudo ufw allow http
sudo ufw allow https

# start
sudo ufw enable