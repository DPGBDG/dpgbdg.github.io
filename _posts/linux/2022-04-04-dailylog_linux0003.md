---
layout: single
title:  "Linux (03) - Network Adapter Driver Fix (TL-WN722N)"

categories:
    - Linux
tags:
    - [Linux, Issue]

toc: true
toc_sticky: true

date: 2022-04-04
last_modified_at: 2020-04-04
---

# TP-Link TL-WN722N V2/V3
- Monitor Mode & Packet Injection Enable
- TL-WN722N V1 enables both mode by default
- V2/V3 Needs special driver to enable those features

## Install
- Install New Driver (driver downloaded & saved on local computer as well)
    ```
    Kali (2022.1) /Parrot (4.11.3) Confirmed

    sudo apt update
    sudo apt upgrade
    sudo reboot
    
    sudo apt install bc
    sudo apt-get install build-essential 
    sudo apt-get install libelf-dev 

    sudo apt-get install linux-headers-`uname -r`
    or (either one of command should work)
    sudo apt-get install linux-headers-5.10.0-kali6-amd64

    sudo apt install dkms
    sudo rmmod r8188eu.ko
    git clone https://github.com/aircrack-ng/rtl8188eus
    cd rtl8188eus
    sudo -i
    echo "blacklist r8188eu" > "/etc/modprobe.d/realtek.conf"
    exit
    sudo reboot

    sudo apt update
    cd rtl8188eus
    sudo make
    sudo make install
    sudo modprobe 8188eu
    ```

## Check
- Enable monitor mode and test packet injection (Internet Disable)
    ```
    sudo ifconfig wlan0 down
    sudo airmon-ng check kill
    sudo iwconfig wlan0 mode monitor
    sudo ifconfig wlan0 up
    iwconfig                             
    sudo aireplay-ng --test wlan0
    ```

- Change back to manage mode (Internet Enable)
    ```
    Method 1
    sudo airmon-ng stop wlan0

    Method 2
    sudo ifconfig wlan0 down
    sudo ifconfig wlan0 mode managed
    sudo wlan0 up

    Method 3
    sudo ifconfig wlan0 up
    service NetworkManager restart
    ```

