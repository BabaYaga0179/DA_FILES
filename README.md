N@lled By: Nguyễn Trung Hậu<br>
Email: ken.hdpro@gmail.com<br>
Facebook: http://fb.com/haunguyenckc<br>
Fork from: https://github.com/irf1404/DA_FILES/

# INSTALL DIRECTADMIN
## Install command for Directadmin 1601 centOS7 centOS8 x64
```bash
yum -y install wget && wget --no-cache -O setup.sh "https://raw.githubusercontent.com/BabaYaga0179/DA_FILES/master/da-1601-centos7-centos8.sh" > tmp 2>&1 && chmod +x setup.sh
```
## Install command for Directadmin 1604 centOS7 centOS8 x64
```bash
yum -y install wget && wget --no-cache -O setup.sh "https://raw.githubusercontent.com/BabaYaga0179/DA_FILES/master/da-1604-centos7-centos8.sh" > tmp 2>&1 && chmod +x setup.sh
```
## Install command for Directadmin 1620 centOS7 x64
```bash
yum -y install wget && wget --no-cache -O setup.sh "https://raw.githubusercontent.com/BabaYaga0179/DA_FILES/master/da-1620-centos7.sh" > tmp 2>&1 && chmod +x setup.sh
```
## Install command for Directadmin 1620 only centOS8 x64
```bash
yum -y install wget && wget --no-cache -O setup.sh "https://raw.githubusercontent.com/BabaYaga0179/DA_FILES/master/da-1620-centos8.sh" > tmp 2>&1 && chmod +x setup.sh
```
## Install command for Directadmin 1624 centOS7 x64
```bash
yum -y install wget && wget --no-cache -O setup.sh "https://raw.githubusercontent.com/BabaYaga0179/DA_FILES/master/da-1624-centos7.sh" > tmp 2>&1 && chmod +x setup.sh
```
## Install command for Directadmin 1624 only centOS8 x64
```bash
yum -y install wget && wget --no-cache -O setup.sh "https://raw.githubusercontent.com/BabaYaga0179/DA_FILES/master/da-1624-centos8.sh" > tmp 2>&1 && chmod +x setup.sh
```

## To Get Help
```bash
./setup.sh -h
```
## To Setup
```bash
./setup.sh m h p i n
```
### Option "m": Mode
+ opsf: Auto setup version package (Default: Openlitespeed, PHP81, PHP74, PHP70, PHP56, Mariadb)
+ auto: Auto setup version package (Default: Openlitespeed, PHP81, Mariadb)
+ normal: You can select version package with custombuild

### Option "h": Server hostname (Default: server.test.com)
+ xxx.yyy.zzz (Ex: server.hca.com)

### Option "p": Password admin
+ You can input password or input: "rand" -> for random password

### Option "i": IP server
+ Auto detect IP if input: detect | or you can input local ip server (Command: "ip a" to show local ip server)

### Option "n": Network Card (Default: hca)
+ For using license.key, Directadmin 1604 no needed config option "n", Other Directadmin version needed config "n"
+ Input network card  attached IP Server


#### Ex: Install DA 1604 in VPS (Do nothing)
+ **Mode**: auto | Host: server.wptop.net | Pass: admin@123 | IP auto detect | Card: hca
```bash
./setup.sh auto server.wptop.net admin@123
```
#### Ex: Install DA version > 1604 in VPS (Set network card for run)
+ **Mode**: auto | Host: server.wptop.net | Pass random | IP auto detect | Card: eth0
```bash
./setup.sh auto server.wptop.net rand detect eth0
```
#### Ex: Install DA version > 1604 in Local Server (Set local IP and network card for run)
+ **Mode**: auto | Host: server.wptop.net | Pass: admin@123 | IP: 1.2.3.4 | Card: eth0
```bash
./setup.sh auto server.wptop.net admin@123 1.2.3.4 eth0
```
#### Ex: Install DA 1604 in Local Server (Set local IP for run)
+ Mode: auto | Host: server.wptop.net | Pass random | IP: 1.2.3.4 | Card: hca
```bash
./setup.sh auto server.wptop.net rand 1.2.3.4
````	

## CONFIG NETWORK IF YOU CONFIG FAIL
```bash
# Download File And View Your VPS Network Card
wget --no-cache -O network.sh "https://raw.githubusercontent.com/BabaYaga0179/DA_FILES/master/network.sh" && chmod +x network.sh
./network.sh
```

## INSTALL SSL FOR ADMINPAGE
```bash
# Point The Subdomain Server.XXX.YYY to IP Server (A Record)
wget --no-cache -O adminssl.sh "https://raw.githubusercontent.com/BabaYaga0179/DA_FILES/master/adminssl.sh" && chmod +x adminssl.sh
./adminssl.sh
```

## INSTALL MULTI PHP VERSION
```
cd /usr/local/directadmin/custombuild
./build set php1_release 8.1
./build set php2_release 7.4
./build set php1_mode lsphp
./build set php2_mode lsphp
./build php n
./build rewrite_confs
```
