# Hackintosh HP EliteBook 840 G3

This repo contains my configuration, kexts, etc of my working hackintosh.

You can also find useful articles on [my blog](https://hologos.github.io).

## macOS versions

List of supported versions:

- macOS Catalina
    - 10.15.1 [(checkout this branch)](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.15.1)
    - 10.15.0 [(checkout this branch)](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.15.0)

- macOS Mojave
    - 10.14.6 [(checkout this branch)](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.14.6)
    - 10.14.5 [(checkout this branch)](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.14.5)
    - 10.14.4 [(checkout this branch)](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.14.4)

## Upgrade guides

- [Upgrade from macOS Mojave to macOS Catalina](https://hologos.github.io/upgrade-from-macos-mojave-to-macos-catalina/)

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

**UPDATE (11/2019):** Since Rehabman is not active for a long time, I migrated to Vanilla Hackintosh method. It means that all kexts are installed to EFI partition to `/EFI/CLOVER/kexts/Other/` (instead of `/Library/Extensions`). I don't update kexts using Rehabman's repo anymore, I use [Kext Updater](https://bitbucket.org/profdrluigi/kextupdater/downloads/).

### Clover bootloader

Current installed version: v2.5k_r5097

### Wifi + BT card

To make a different Wifi card work, follow this guide [Broadcom WiFi/Bluetooth [Guide]](https://www.tonymacx86.com/threads/broadcom-wifi-bluetooth-guide.242423/). All necessary kexts and changes are included with my EFI for BCM94352Z/AW-CE162NF/DW1560.

**UPDATE (10/2019):** Rehabman is currently not active so I migrated to [acidanthera's BT kexts](https://github.com/acidanthera/BrcmPatchRAM) (Mieze's patches included). These kexts are included in my EFI folder.

If you install hackintosh by yourself, download latest BT kexts from Releases page and copy `BrcmPatchRAM3.kext`, `BrcmFirmwareData.kext` and `BrcmBluetoothInjector.kext`) to `/EFI/CLOVER/kexts/Other/`.

### Enabling HiDPI

To set custom HiDPI resolution, use this [website](https://comsysto.github.io/Display-Override-PropertyList-File-Parser-and-Generator-with-HiDPI-Support-For-Scaled-Resolutions/) or follow this guide [Adding/Using HiDPI custom resolutions](https://www.tonymacx86.com/threads/adding-using-hidpi-custom-resolutions.133254/).

Necessary file generated with aforementioned website is included in HiDPI folder.

### FileVault 2

I started using FileVault to protect my data. All necessary drivers are present in the EFI folder.

### Donation

If you like what I do and you found this repository helpful, you can

<a href="https://www.buymeacoffee.com/hologos" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>
