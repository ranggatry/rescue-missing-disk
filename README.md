# Using Ubuntu live cd 18.04 (Live CD)
### How to Fix Disk Lost Partition on Ubuntu 18.04 Live CD
- jalankan vm ubuntu 18.04 desktop sebagai live cd di sda
- attach disk yang corrup di sdb

### Initial setup
passwd root
apt-get update && apt-get install openssh-server
nano /etc/ssh/sshd_config
ubah permit root login jadi yes
/etc/init.d/ssh restart

### Ubah repo
ubah repo ke sini /etc/apt/sources.list
deb http://kambing.ui.ac.id/ubuntu/ bionic main restricted
deb http://kambing.ui.ac.id/ubuntu/ bionic-updates main restricted
deb http://kambing.ui.ac.id/ubuntu/ bionic universe
deb http://kambing.ui.ac.id/ubuntu/ bionic-updates universe
deb http://kambing.ui.ac.id/ubuntu/ bionic multiverse
deb http://kambing.ui.ac.id/ubuntu/ bionic-updates multiverse
deb http://kambing.ui.ac.id/ubuntu/ bionic-backports main restricted universe multiverse
deb http://kambing.ui.ac.id/ubuntu/ bionic-security main restricted
deb http://kambing.ui.ac.id/ubuntu/ bionic-security universe
deb http://kambing.ui.ac.id/ubuntu/ bionic-security multiverse

### Install testdisk
apt-get update
apt-get install testdisk 

### Install boot-repair
sudo add-apt-repository ppa:yannubuntu/boot-repair
apt-get update
apt-get install boot-repair -y

### Jalankan testdisk
testdisk /dev/sda
proceed
pilih intel
pilih analyse
quick search
pilih partisi yang akan di write ke disk
pilih write

### Jalankan boot-repair
boot-repair
pilih recommended repair
copas prompt script to terminal dan jalankan
lalu klik forward di ui
copas prompt script to terminal dan jalankan
lalu klik forward di ui# rescue-missing-disk
