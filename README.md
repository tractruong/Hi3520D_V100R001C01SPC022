# Hi3520D_V100R001C01SPC022

## Update commmand to compile on Ubuntu 18.04
$ lsb_release -a
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 18.04.6 LTS
Release:	18.04
Codename:	bionic

$ uname -a
Linux ubuntu 5.4.0-90-generic #101~18.04.1-Ubuntu SMP Fri Oct 22 09:25:04 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux

## Update package
sudo apt update
sudo apt install u-boot-tools
sudo apt install zlib1g-dev
sudo apt install libc6-i386 lib32stdc++6 lib32gcc1 lib32ncurses5

##Setup SDK
Refer to Hi3520D_V100R001C01SPC022/01.software/board/documents_en/Description of the Installation and Upgrade of the Hi3520D SDK.txt

cp -rv Hi3520D_V100R001C01SPC022/01.software/board/Hi3520D_SDK_V1.0.2.2 ~/
cd ~/Hi3520D_SDK_V1.0.2.2
chmod +x run.unpack
./run.unpack

## cloning osdrv from git repo
rm -r osdrv
git clone https://github.com/rgmabs19357/Hi3520D_V100R001C01SPC022_osdrv.git

## apply patch


## Compile all
make OSDRV_CROSS=arm-hisiv100nptl-linux CHIP=hi3520d OSDRV_SIZE=full all
