# Hi3520D_V100R001C01SPC022
Feasible checking for compiling on HOST
```
$ lsb_release -a
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 18.04.6 LTS
Release:	18.04
Codename:	bionic

$ uname -r
5.4.0-90-generic
```

Reference
> 01.software/board/documents_en/Description of the Installation and Upgrade of the Hi3520D SDK.txt

## Unpack package
```
cd 01.software/board/Hi3520D_SDK_V1.0.2.2/Hi3520D_SDK_V1.0.2.2
chmod +x sdk.unpack
./sdk.unpack
```
(*) This repo do not include osdrv, to recompile it please refer to Hi3520D_V100R001C01SPC022_osdrv 

## Setup cross compiler 
```
source /etc/profile

cd ../../
sudo dpkg-reconfigure dash -> NO

```

(*) For install cross compiler please refer to Hi3520D_V100R001C01SPC022_osdrv 



## Compile
### drv hisi-irda

(*) please refer to Hi3520D_V100R001C01SPC022_osdrv to get kernel source code

```
ln -s Hi3520D_V100R001C01SPC022_osdrv/osdrv Hi3520D_SDK_V1.0.2.2/osdrv
export HIWORK_PATH=`pwd` ( path to Hi3520D_SDK_V1.0.2.2)
cd drv/hisi-irda
make
```

### mmp sample 

```
cd mmp/samples
make
```
