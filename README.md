# Hackintosh HP EliteBook 840 G3

This repo contains my configuration, kexts, etc of my working hackintosh.

## macOS versions

List of supported versions:

- macOS Catalina
    - 10.15.0 [(checkout this branch)](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.15.0)

- macOS Mojave
    - 10.14.6 [(checkout this branch)](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.14.6)
    - 10.14.5 [(checkout this branch)](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.14.5)
    - 10.14.4 [(checkout this branch)](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/10.14.4)

## Upgrade guides

- [Upgrade from macOS Mojave to macOS Catalina](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/wiki/Upgrade-from-macOS-Mojave-to-macOS-Catalina)

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

### Clover bootloader

Current installed version: v2.5k_r5097

### Wifi + BT card

To make a different Wifi card work, follow this guide [Broadcom WiFi/Bluetooth [Guide]](https://www.tonymacx86.com/threads/broadcom-wifi-bluetooth-guide.242423/). All necessary kexts and changes are included with my EFI for BCM94352Z/AW-CE162NF/DW1560.

**UPDATE (10/2019):** Rehabman is currently not active so I migrated to [Mieze's BT kexts](https://github.com/Mieze/OS-X-BrcmPatchRAM-Catalina). Download latest BT kexts from thread [BrcmPatchRAM2 for 10.15 Catalina](https://www.insanelymac.com/forum/topic/339175-brcmpatchram2-for-1015-catalina-broadcom-bluetooth-firmware-upload/?page=6) (`BrcmPatchRAM3.kext`, `BrcmFirmwareRepo.kext` and `BrcmBluetoothInjector.kext`) and copy them to `/Library/Extensions`.

Since macOS Catalina, system partition is read-only, you have to mount it first as read-write:

```bash
sudo mount -uw /
```

To rebuild kext cache:

```bash
sudo chown -v -R root:wheel /System/Library/Extensions
sudo touch /System/Library/Extensions
sudo chmod -v -R 755 /Library/Extensions
sudo chown -v -R root:wheel /Library/Extensions
sudo touch /Library/Extensions
sudo kextcache -i /
```

### Enabling HiDPI

To set custom HiDPI resolution, use this [website](https://comsysto.github.io/Display-Override-PropertyList-File-Parser-and-Generator-with-HiDPI-Support-For-Scaled-Resolutions/) or follow this guide [Adding/Using HiDPI custom resolutions](https://www.tonymacx86.com/threads/adding-using-hidpi-custom-resolutions.133254/).

Necessary file generated with aforementioned website is included in HiDPI folder.

### FileVault 2

I started using FileVault to protect my data. I won't merge the support to master for now as I will leave it in a separate branch [feature/filevault2-support-clover-v2.5k](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/tree/feature/filevault2-support-clover-v2.5k).

If you want to use it as well, just checkout `feature/filevault2-support-clover-v2.5k` branch and update EFI folder accordingly.

Verify:

1) `EFI/CLOVER/drivers/UEFI/AppleImageCodec.efi` is removed (otherwise booting will take 5 minutes).
2) `EFI/CLOVER/drivers/UEFI/AppleGenericInput.efi` and `EFI/CLOVER/drivers/UEFI/AppleUiSupport.efi` are present.
3) `Preboot` partition is not listed in Hidden volumes (or you will not be able to boot).

When this is done, you can enable FileVault in settings.

## Issues

- Trackpad stops working sometimes, I don't know why for now *(workaround in [Issue #1](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/issues/1))*.
- Mute button doesn't work *([Issue #2](https://github.com/Hologos/hackintosh-hp-elitebook-840-g3/issues/2))*.
