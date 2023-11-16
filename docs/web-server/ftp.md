---
layout: default
title: Configure FTP Server
nav_order: 3
parent: Web Server Configuration
---
# Configure FTP Server

We will use `vsftpd` to configure ftp server.

Install `vsftpd`:
```console
sudo apt install vsftpd
```

to change some basic configuration we have to update **`/etc/vsftpd.conf`** file

```console
sudo nano /etc/vsftpd.conf
```

Make sure the following configurtion:

```
local_enable=YES
write_enable=YES
```

You also may need to change the root directory of FTP Server like this:

```
local_root=/var/www/html
```

After the **`vsftpd.conf`** file update restart the application

```console
sudo systemctl restart vsftpd
```