# Hackintosh HP EliteBook 840 G3

This repo contains my configuration, kexts, etc of my working hackintosh.

## macOS versions

List of supported versions:

- macOS Mojave
    - versions: 10.14.6 [[master branch]](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/master)
    - versions: 10.14.5 [[tag 10.14.5]](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.14.5)
    - versions: 10.14.4 [[tag 10.14.4]](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.14.4)

## Specs

**BIOS:** N75 (ver. 01.20)

**CPU:** Intel Core i5 6300U @ 2.4 GHz (Skylake, 2 cores, 4 HT)

**Chipset:** Intel 100 Series

**GPU:** integrated Intel HD Graphics 520

**Display:** 1920x1080

**Ethernet:** Intel I219LM

**Wifi + BT:** BCM94352Z/AW-CE162NF/DW1560 (M.2, supports WiFi/ac and BT4LE)

## Installation

***Notice: you have to generate your own SMBIOS/SerialNumber and SMBIOS/BoardSerialNumber.***

You can either install your hackintosh all by yourself or you can use my EFI folders to install and run the hackintosh.

To install hackintosh on your laptop, follow these 2 guides:

- [[Guide] Booting the OS X installer on LAPTOPS with Clover](https://www.tonymacx86.com/threads/guide-booting-the-os-x-installer-on-laptops-with-clover.148093/)
- [[Guide] HP ProBook/EliteBook/Zbook using Clover UEFI hotpatch](https://www.tonymacx86.com/threads/guide-hp-probook-elitebook-zbook-using-clover-uefi-hotpatch.261719/)

### Wifi card

To make a different Wifi card work, follow this guide [Broadcom WiFi/Bluetooth [Guide]](https://www.tonymacx86.com/threads/broadcom-wifi-bluetooth-guide.242423/). All necessary kexts and changes are included with my EFI for BCM94352Z/AW-CE162NF/DW1560.

### Enabling HiDPI

To set custom HiDPI resolution, use this [website](https://comsysto.github.io/Display-Override-PropertyList-File-Parser-and-Generator-with-HiDPI-Support-For-Scaled-Resolutions/) or follow this guide [Adding/Using HiDPI custom resolutions](https://www.tonymacx86.com/threads/adding-using-hidpi-custom-resolutions.133254/).

Necessary file generated with aforementioned website is included in HiDPI folder.

## Issues

*no known issues*
