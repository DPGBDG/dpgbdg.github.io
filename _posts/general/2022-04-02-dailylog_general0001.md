---
layout: single
title:  "Basic System Usage Tips (01) - USB Partition Error"

categories:
    - General
tags:
    - [General, Basic, Tips]

toc: true
toc_sticky: true

date: 2022-04-02
last_modified_at: 2020-04-02
---

# USB Partition Merge

## Simple Way
- Using Windows Default Tool

    ```
    My PC > Right Click > Manage > Disk Management > Merge usb partition from here
    ```
## Harder Way (Unable to merge from disk management)
- Using Terminal

    ```
    1. Window key + X
    2. Windows PowerShell
    3. Diskpart
    4. List Disk   (Check USB Number here)
    5. Sel Disk Number
    6. Clean
    7. Convert GPT  (Only for disk with higher than 2 GB)
    8. Create partition primary
    9. Sel par 1
    10. Format fs=ntfs quick
    11. Assign (Only for disk with higher than 2 GB)
    12. Active (Only for disk with higher than 2 GB)
    ```
