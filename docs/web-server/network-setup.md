---
layout: default
title: Network Setup
nav_order: 4
parent: Web Server Configuration
---
# Configure Network with Static IP

In my case i will set my Server IP into `192.168.47.70`, to do this locate the `netplan` configuration file.
```console
sudo nano /etc/netplan/00-installer-config.yaml
```
And make change like this:

```yml
network:
  ethernets:
    eno1:
      addresses:
        - 192.168.47.70/24
#        - 192.168.47.71/24 You can also set another ip like this
      routes:
         - to: default
           via: 192.168.47.1 #This is the Gateway
      nameservers:
        addresses: [8.8.8.8]
  version: 2
  renderer: networkd
```

After making the change save the file and apply netplan configuration:

```console
netplan apply
```