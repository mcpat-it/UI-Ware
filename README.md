<p align="center">
  <img class="comment" src="images/UIWare.svg" alt="UI-Ware"/>
</p>

# UI-Ware for UnifiOS (UDM, UDR, UXG)
[![Donate to this project using PayPal](https://shields.io/badge/Paypal-Donate-blue?logo=paypal&style=flat)](https://www.paypal.com/donate/?business=2667RS4MQ9M5Y&no_recurring=1&item_name=Please+support+me+if+you+like+my+work.+Thank+you%21&currency_code=EUR)
[![Donate to this project using Buy Me A Coffee](https://shields.io/badge/Buy%20me%20a%20coffee-Donate-yellow?logo=buymeacoffee&style=flat)](https://buymeacoff.ee/mcpat)
[![LICENSE](https://shields.io/badge/license-GPL-lightgrey)](https://raw.githubusercontent.com/pwallner/UI-Ware/main/LICENSE)
[![Platform](https://shields.io/badge/platform-linux--64%20(aarch64)-lightgrey)](https://github.com/pwallner/UI-Ware)
[![GitHub issues open](https://img.shields.io/github/issues/pwallner/UI-Ware.svg)](https://github.com/pwallner/UI-Ware/issues)
[![Downloads total](https://img.shields.io/github/downloads/pwallner/UI-Ware/total)](https://github.com/pwallner/UI-Ware/releases)
[![Latest release](https://img.shields.io/github/v/release/pwallner/UI-Ware)](https://github.com/pwallner/UI-Ware/releases)

[![forks](https://img.shields.io:/github/forks/pwallner/UI-Ware?style=social)](https://github.com/pwallner/UI-Ware)
[![stars](https://img.shields.io:/github/stars/pwallner/UI-Ware?style=social)](https://github.com/pwallner/UI-Ware)
[![watchers](https://img.shields.io:/github/watchers/pwallner/UI-Ware?style=social)](https://github.com/pwallner/UI-Ware)
[![followers](https://img.shields.io:/github/followers/pwallner?style=social)](https://github.com/pwallner)

## Project Notes

**Author:** Patrick Wallner

Based on Optware, a software repository for embedded devices which use the [Linux kernel](https://www.kernel.org/linux.html), arised the idea of UI-Ware for UnifiOS devices. Installing UI-Ware allow users to take advantage by adding software to the device which permits it to perform new tasks or provide other features besides those they were marketed for, or simply to perform those functions better.

Please see below for instructions on how to install UI-Ware and associated utils.

## Table of Contents

  * [Install](#install)
  * [How to use UI-Ware](#how-to-use-ui-ware)
  * [Upgrades](#upgrades)
  * [Packages](#packages)
  * [The future of UI-Ware](#the-future-of-ui-ware)
  * [Support my work](#support-my-work)
  * [FAQ](#faq)


## Install
> ⚠️ **Cause of lacking of all devices, this is only tested on my UDM Base and will only work for v2.4.x and greater!** 

Two simple steps:

1. Connect to your device via SSH and type the following command to download and install UI-Ware. NOTE: always [this link](https://github.com/pwallner/UI-Ware/releases) check for the latest release.

    ```sh
    cd /tmp && wget https://ui-ware.mcpat.com/repo/ui-ware_1.0.0_all.deb && dpkg -i ui-ware_1.0.0_all.deb &&  rm ui-ware_1.0.0_all.deb
    ```
or

1. Alternative you can use an automated script **setup-uiware.sh** as shown below [⚠️NOT WORKING YET!!]

    ```sh
    cd /tmp
    wget https://ui-ware.mcpat.com/src/setup-uiware.sh
    chmod +x setup-uiware.sh
    ./setup-uiware.sh
    ```
    
2. Check installation:

    ```sh
    systemctl status ui-ware
    ```
    
 This will install the complete ui-ware system to `/mnt/.rwfs/data/data/opt` as well as create a link to the `/opt` folder and finally start the service `ui-ware`.  

## How to use UI-Ware
It's like a debian system, use the `apt` commands like `apt-get install <package>`.

## Upgrades
Upgrades can be done by `apt-get update` and `apt-get upgrade`. Please note, that all files from UI-Ware will be installed in "opt", system files will stay untouched.

## Packages
The main reason for developing the UI-Ware were the missing features:
 - NFS server/client for easy exchange of data [TBA]
 - CIFS server (client) for easy exchange of data [TBA]
 - OpenVPN server (client) [TBA]
 - Wireguard[^1] [TBA]
 - FTP server [TBA]

But during developing of the first feature (NFS), I generated 170 software packages because I was compiling directly on my own UDM. Don't ask why, I had my reasons...

So I can provide now additionly fully functional apps:

 - GCC 12.2.0
 - Perl
 - Python
 - Make
 - Binutils
 - wireguard tools
 - ftp
 - Git
 - Git-lfs
 
and many many more.
## The future of UI-Ware
Maybe sime developers will assist and provide packages. Maybe orher repos can find here new home.

## Support my work
I'm a working single dad and this is only my hobby which I did in my rare free time. So I really appreciate if you make a small donation to let me buy some sweets for my son!

[!["Buy Me A Coffee"](images/coffee.png)](https://buymeacoff.ee/mcpat)
[![Support via PayPal](images/paypal.svg)](https://www.paypal.com/donate/?business=2667RS4MQ9M5Y&no_recurring=1&item_name=Please+support+me+if+you+like+my+work.+Thank+you%21&currency_code=EUR)
<!-- [![Donate](https://www.paypalobjects.com/en_US/AT/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/donate/?business=2667RS4MQ9M5Y&no_recurring=1&item_name=Please+support+me+if+you+like+my+work.+Thank+you%21&currency_code=EUR) -->
[![Donate](images/QR-Code.png)](https://www.paypal.com/donate/?business=2667RS4MQ9M5Y&no_recurring=1&item_name=Please+support+me+if+you+like+my+work.+Thank+you%21&currency_code=EUR)
## FAQ

<details markdown='1'>

<summary>A package is missing in the repo, what can I do</summary>
	
 - Send a request, you know I'm a busy man, but maybe I can help
 - Compile a package, send it to me, I can add it to the repo[^2]

</details>

[^1]:Special thx to the [wireguard-kmod](https://github.com/tusc/wireguard-kmod) team for support and the code which I can use.
[^2]:See guidelines to follow [TBC]
