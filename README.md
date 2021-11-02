# Unofficial Droidian port for Xiaomi MI 8

This repo contains kernel source and building files. 

### What is working? Not working? Working but not tested?
Feature   | Working(w) or not(n)/not tested(nt)
---------:|:-----------------
Boots into UI | nt
Touchscreen | nt
WiFi | nt
Manual Brightness | nt
Battery Percentage | nt
Charging | nt
Off-mode Charging | nt
Airplane Mode | nt
Power Option Execution | nt
Camera | nt
MTP | nt
ADB | nt
Screen Rotation | nt
Sound | nt
Vibration | nt
Torch | nt
Mobile Data | nt
Battery Life | nt
Mobile Hotspot | nt
Anbox Kernel Patches | nt
Proximity Sensor | nt
GPS | nt
Carrier Info | nt
Calling | nt
MMS | nt
Network PIN Unlock | nt
SMS | nt
Voice in Calls | nt



How to install
===
Initialize directories and repo
---
``` 
# This commands are done on host computer
KERNEL_DIR="$HOME/droidian/kernel/xiaomi/dipper/"
PACKAGES_DIR="$HOME/droidian/packages"
mkdir -p $HOME/droidian/kernel/xiaomi
mkdir -p $PACKAGES_DIR
git clone https://github.com/droidian-dipper/droidian-kernel-xiaomi-dipper.git $KERNEL_DIR/dipper/
cd $KERNEL_DIR
git checkout -b bullseye
```

Run Docker container and build packages
---
```
(host)$ docker run -v $PACKAGES_DIR:/buildd -v $KERNEL_DIR:/buildd/sources -it quay.io/droidian/build-essential:bullseye-amd64 bash # Still on host
(docker)$ cd /buildd/sources/ && RELENG_HOST_ARCH="arm64" releng-build-package
```
If everything goes well, built packages will be located in ~/droidian/packages/ directory.

If there are any issues, please contact me in [Telegram Group](https://t.me/DroidianLinux). My nickname is @gnu_stallman. Or create issue on this repo.
