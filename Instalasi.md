# Tugas-IV

## Instalasi
### Install SNORT
#### 1. Cara Ribet
Update Dependencies
```sh
sudo apt-get install build-essential libpcap-dev libpcre3-dev libdumbnet-dev bison flex zlib1g-dev libdnet
```
Download daq
```sh
wget https://www.snort.org/downloads/snort/daq-2.0.6.tar.gz
```
Extract daq
```sh
tar -xvzf daq-2.0.6.tar.gz
cd daq-2.0.6
```
Install daq
```sh
./configure
make
sudo make install
```
Download snort
```sh
cd ~/snort_src
wget https://www.snort.org/downloads/snort/snort-2.9.8.0.tar.gz
```
Install snort
```sh
./configure --enable-sourcefire
make
sudo make install
cd ../
```

#### 1. Cara Gampang
```sh
sudo apt-get install snort
```

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
