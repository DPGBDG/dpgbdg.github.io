---
layout: single

title:  "Linux (04) -  Linux Full Installation On USB"

categories:
    - Linux
tags:
    - [Linux, Install, Issue]

toc: true
toc_sticky: true

date: 2022-04-08
last_modified_at: 2020-04-08
---


# Linux USB Install Problem

## Bootable live USB
- Type of Live USB  
  
    1) Live USB - Fast, Read Only, Unable to save any data, resets every time restart  
    2) Live USB (Persistence Mode) - Require persistence memory when creating live usb, Slow (Require Fast Read/Write USB Memory stick), Data can be saved.


## Full Installation on USB/SSD 
- Instruction  
  
    1) extra bootable USB required  
    2) Fast Read/Write USB/SSD required  
    3) GRUB can cause some issues (Booting order should change after installation)  
    4) Must install GRUB on Memory Stick (USB/SSD)  
    5) Memory stick partition should be created  
   
        ```
        Partition 1 (Main) (/dev/sda/)
        Ubuntu Installation Example
        Size = Any (Large Amount)
        Type for the new partition = Primary
        Location for the new partition = Beginning of this space
        Use as = Ext4 journaling file system
        Mount point = /

        Partition 2 (Swap) (Optional but it's for memory)
        Ubuntu Installation Example
        Size = Any (small Amount few Gb)
        Type for the new partition = Logical
        Location for the new partition = Beginning of this space
        Use as = swap area
        ```

## Delete Linux and Boot loader
- Instruction  
  
    1. Delete Linux volume from disk
        ```
        Computer Management > Disk Management > Delete Linux volume
        ```
    2. Delete Boot Loader
        ```
        System > Recovery > Advanced start option > Troubleshoot > Advanced Option > Command Prompts >
            Diskpart
            List disk           (Find window installed disk number)
            Select disk #
            list volume         (Find FAT32 partition with Hidden)
            Select volume #
            assign letter m     (Any un-assigned letter can be assigned)
            exit
            m:                  (Enter m: folder)
            cd efi
            dir                 (Find Linux folder name)
            rd linux_folder_name /s
            dir                 (Check folder deleted)
            exit                (reboot)
                                (Check Boot Loader)
        ```


# Issue
## Window boot manager is deleted
- Unable to boot using default window booting menu    
    ```
    Install Window boot manager, by using attached program (bootice_v1.3.4.0.exe)
    Start bootice_v1.3.4.0.exe
    Physical disk tab > Destination Disk (Window Installed Disk) > Process MBR > Windows NT 5.x / 6.x MBR (Window 10 up = 6.x) > Install / Config
    ```
## Delete Boot Loader using "bootice"
- Deleting Boot menu using 3rd party program
    ```
    Start bootice_v1.3.4.0.exe
    UEFI > Edit Boot Entries > Delete boot menu
    ```
