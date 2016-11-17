# Laporan Tugas 4
## Instalasi
### Install SNORT
##### Update Dependencies
```sh
sudo apt-get install build-essential libpcap-dev libpcre3-dev libdumbnet-dev bison flex zlib1g-dev libdnet
```
#### 1. Cara Ribet

Download dan install daq
```sh
wget https://www.snort.org/downloads/snort/daq-2.0.6.tar.gz

tar -xvzf daq-2.0.6.tar.gz
cd daq-2.0.6

./configure
make
sudo make install
cd ../
```
Download dan install snort
```sh
wget https://www.snort.org/downloads/snort/snort-2.9.8.0.tar.gz

tar -xvzf snort-2.9.8.0.tar.gz
cd snort-2.9.8.0

./configure --enable-sourcefire
make
sudo make install
cd ../
```
#### Membuat SNORT sebagai NIDS
Update shared library
```sh
sudo ldconfig
```
Tambahkan symbolic link
```sh
sudo ln -s /usr/local/bin/snort /usr/sbin/snort
```
Gandakan konfigurasi ke **/etc/snort/**
```sh
sudo cp ~/snort_src/snort-2.9.8.0/etc/*.conf* /etc/snort
sudo cp ~/snort_src/snort-2.9.8.0/etc/*.map /etc/snort
```

#### 2. Cara Gampang
```sh
sudo apt-get install snort
```
Dengan cara ini, rules sudah ada di 
```sh
/etc/snort/
```
jadi untuk menggunakan rules tinggal include file yang ada di direktori di atas



### Install IDSWakeup
#### Install Dependencies
IDSWakeup butuh beberapa dependencies sebelum dijalankan
```
sudo apt-get install --yes build-essential autoconf libtool make libnet1
```
Untuk jaga-jaga IDSWakeup butuh libnet1, maka install libnet1 
```sh
mkdir idswakeup

wget http://packetfactory.openwall.net/libnet/dist/deprecated/libnet-1.0.2a.tar.gz -O libnet-1.0.2a.tar.gz 

tar xvf libnet-1.0.2a.tar.gz

cd Libnet-1.0.2a

./configure
sudo make install

cd ../
```
Download dan install IDSWakeup
```sh
wget http://www.hsc.fr/ressources/outils/idswakeup/download/IDSwakeup-1.0.tgz -O IDSwakeup-1.0.tgz

tar xvf IDSwakeup-1.0.tgz

cd IDSwakeup-1.0

make

cd ..
```
