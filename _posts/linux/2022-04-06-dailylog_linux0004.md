---
layout: single
title:  "Linux (04) - Parrot OS Network ID Issue"

categories:
    - Linux
tags:
    - [Linux, Issue]

toc: true
toc_sticky: true

date: 2022-04-06
last_modified_at: 2020-04-06
---

# Parrot OS Wireless Network ID Issue fix
- In Parrot OS, network ID can show alphanumeric combination (wlxXXXXXXXXXXXX).
- Very difficult to type network ID
- Change it to normal wlan#
    ```
    Start terminal
    cp /lib/udev/rules.d/80-net-setup-link.rules /etc/udev/rules.d/
    cd /etc/udev/rules.d/
    gedit 80-net-setup-link.rules
        change $env{ID_NET_NAME} to {ID_NET_SLOT}
    ```
