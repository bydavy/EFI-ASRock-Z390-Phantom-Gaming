# Vanilla Hackintosh running MacOS Mojave

![geekbench](https://raw.githubusercontent.com/bydavy/EFI-ASRock-Z390-Phantom-Gaming-data/master/images/geekbench.png)
![neofetch](https://raw.githubusercontent.com/bydavy/EFI-ASRock-Z390-Phantom-Gaming-data/master/images/neofetch.png)

## Introduction

### Hardware

* [Intel Core i9-9900K](https://amzn.to/2Cr0dFy)
* [ASRock Z390 Phantom Gaming-ITX/AC](https://amzn.to/2T3ju7d)
* [Corsair LPX 32GB (2x16GB) 3200MHz DDR4](https://amzn.to/2ATIeYC)
* [Samsung 970 EVO 2TB - NVMe PCIe M.2](https://amzn.to/2Dk4wnL)
* [CORSAIR SF Series, SF600, SFX](https://amzn.to/2T1fYu8)
* [Louqe GHOST S1](http://www.louqe.com/)
* [Fractal Design Celsius S24](https://amzn.to/2W4Zent)
* [BCM20702 Bluetooth USB Adapter](https://www.ebay.com/itm/Wireless-Bluetooth-4-0-Dual-Mode-USB-Broadcom-BCM20702-Adapter-Dongle-Receiver-1/231835142274?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2060353.m2749.l2649)

![build](https://raw.githubusercontent.com/bydavy/EFI-ASRock-Z390-Phantom-Gaming-data/master/images/build.jpg)

### What works

* Integrated GPU with hardware acceleration
* Audio
* Ethernet
* Bluetooth (usb adapter)
* Sleep

### What doesn't work

* Wi-Fi (can be fixed with usb adapter)
* Thunderbolt Type-C

## Installation

### Motherboard

Flash [bios 1.50](https://www.asrock.com/mb/Intel/Z390%20Phantom%20Gaming-ITXac/index.asp#BIOS).

Change the following settings:

* Advanced > Chipset Configuration > VT-d -> Disabled
* Advanced > USB Configuration > XHCI Hand-off -> Enabled

### MacOs Mojave

1. Create a bootable USB stick
2. Mount EFI
3. git clone https://github.com/bydavy/EFI-ASRock-Z390-Phantom-Gaming.git .
4. Install MacOS
5. Mount your EFI partition from the hard drive with Clover Configurator and copy EFI from usb stick to hard drive

## Context

### Kext

1. Audio
 * AppleALC.kext
 * VoodooHDA.kext
2. Bluetooth
 * BrcmFirmwareRepo.kext
 * BrcmPatchRAM2.kext
3. Ethernet
 * IntelMausiEthernet.kext

### Sleep

* Crash on sleep: fix was to install EmuVariableUefi-64.efi
* Sleep wake cycle: fix was a custom DSDT (somehow an XDCI device was waking it up)

### USB mapping

This EFI has a [custom DSDT](https://github.com/bydavy/EFI-ASRock-Z390-Phantom-Gaming-data) to map USB ports used.

## Files

Go to the [data repository](https://github.com/bydavy/EFI-ASRock-Z390-Phantom-Gaming-data).
