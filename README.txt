*********************************************
Scripts to install Ubuntu/Debian fo Odroid-c1
*********************************************

Tested on Ubuntu trusty & utopic host.


You need to install following packages on your machine:

sudo apt-get install debootstrap qemu-user-static

Edit "create-sdcard" & "second-stage" scripts to configure installer to your needs.

View script comments for more details.

======================================

Script create minimal system whitch can be the base for installing server or desktop system.

For typical server install (recommended):

  sudo apt-get install parted btrfs-tools rsync aptitude apache2 php5 samba cifs-utils pure-ftpd shorewall nfs-kernel-server
  sudo apt-get install mysql-server phpmyadmin
  sudo apt-get install firebird2.5-super php5-interbase
  sudo apt-get install build-essential libssl-dev
  
TIP: for mysql and firebird set server bind adress to 0.0.0.0 in config files !

Install webmin:
---------------
sudo su (or login as root)
wget http://www.webmin.com/jcameron-key.asc
apt-key add jcameron-key.asc
rm jcameron-key.asc
echo "deb http://download.webmin.com/download/repository sarge contrib" >> /etc/apt/sources.list
apt-get update
apt-get install webmin
apt-get clean
exit

Install node.js
---------------
sudo su (or login as root)
curl -sL https://deb.nodesource.com/setup | bash -
apt-get install nodejs




============================================
If you want to create the desktop system run

sudo install_desktop
or
sudo install_mini_desktop

and reboot
============================================


****************************
* RESIZING ROOT PARTITION: *
****************************

run:
sudo fs_resize


