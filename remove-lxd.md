

Complete this!!

lxd is recommended by ubuntu-server

root@c7:~# lsb_release -a No LSB modules are available. Distributor ID: Ubuntu Description: Ubuntu 16.04 LTS Release: 16.04 Codename: xenial

root@c7:~# apt-cache depends ubuntu-server|grep lxd Recommends: lxd

root@c7:~# apt-cache depends ubuntu-server|grep Recommends Recommends: lxd Recommends: snapd

You can use

apt install --no-install-recommends ubuntu-server

to avoid installing lxd and snapd or

apt remove --purge lxd snapd

to remove these without removing ubuntu-server

root@c7:~# apt remove --purge lxd snapd Reading package lists... Done Building dependency tree
Reading state information... Done The following packages will be REMOVED: lxd* snapd* 0 upgraded, 0 newly installed, 2 to remove and 0 not upgraded. After this operation, 37.4 MB disk space will be freed. Do you want to continue? [Y/n] (Reading database ... 25405 files and directories currently installed.) Removing lxd (2.0.0-0ubuntu4) ... Warning: Stopping lxd.service, but it can still be activated by: lxd.socket Purging configuration files for lxd (2.0.0-0ubuntu4) ... Failed to stop lxd.service: Unit lxd.service not loaded. dpkg: warning: while removing lxd, directory '/var/lib/lxd' not empty so not removed Removing snapd (2.0.3) ... Purging configuration files for snapd (2.0.3) ... Processing triggers for man-db (2.7.5-1) ...
