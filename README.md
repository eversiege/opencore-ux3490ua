# 🚧 THIS IS A TEMPLATE!

This repo is intended to be used as a template for those wanting to share their OpenCore EFI files with others on GitHub, also providing helpful setup information.

Things to replace:
- ~~``CPU_MODEL`` (e.g. Intel® Core™ i9-10900K)~~
- ~~``CPU_GENERATION`` (e.g. Comet Lake)~~
- ~~``CHIPSET_MODEL`` (e.g. Z490)~~
- ~~``GPU_MODEL`` (e.g. AMD RX 5700 XT)~~
- ~~``GPU_INTEGRATED_MODEL`` (e.g. Intel UHD 630)~~
- ~~``MOTHERBOARD_MODEL`` (e.g. ASUS ROG STRIX Z490-E GAMING)~~
- ~~``VERSION_NAME`` (e.g. macOS Sonoma)~~
- ~~``HOST_RAM`` (e.g. 64 GB DDR4 3200MHz)~~
- ``STORAGE_MODEL`` (e.g. 500 GB WD Blue NVMe) | should I? this laptop houses a nvme not supported by opencore, but is working flawlessly with the latest firmware patch
- ``ETHERNET_MODEL`` (e.g. Intel I225-V 2.5Gb) | i forgor
- ~~``DISABLED_GPU_MODEL`` (e.g. NVIDIA RTX 3090)~~
- ``SECURE_BOOT_MODEL`` (e.g. j185f) | as if I knew that one
- ``BOOT_ARGS`` (e.g. ``-v keepsyms=1``)
- ~~``MAC_MODEL`` (e.g. iMac20,2)~~

Other things to change:
- Problem list, including any fixes
- Your SSDT tables in the **ACPI** section
- Any added **DeviceProperties** sections
- Any additional kexts you use in **Kernel**
- Any patches you may have added in **Kernel**
- Any other **NVRAM** contents
- Your chosen **SMBIOS** Mac model, ~~and why you chose it~~
- The drivers you use in **UEFI**
- A gallery of your working setup in **Gallery**
- Your disclaimers in **Disclaimer**

<br>

### You can see a completed example of my setup here: [**OpenCore-Z490E-CometLake**](https://github.com/Coopydood/OpenCore-Z490E-CometLake)

<br>

**REMEMBER TO DELETE THIS SECTION BEFORE FINISHING!**


***


# OpenCore ASUS UX390UA for Intel Kaby Lake
This is an OpenCore Hackintosh configuration example for ASUS UX390UA laptop with Intel Kaby Lake processor. This repository has all information you need to run Ventura on this machine.

[This OpenCore configuration is a modified template by @Coopydood. This text will lead to the source project.](https://github.com/Coopydood/OpenCore-Z490E-CometLake)

> [!WARNING]
> This GitHub repository does not serve as the definitive solution, as the critical issues indicated in Problems section are yet to be solved.

<img src="#" alt="Image" width="1400"/>
<p align="center"></p>

<br>

## What works?

### macOS

- [x] macOS Ventura
- [ ] macOS Sonoma (and beyond)

### Hardware

- [x] iGPU (Intel HD Graphics 620)
- [x] NVMe drive
- [x] USB 3.1 (XHCI)
- [ ] Ethernet (not tested)
- [x] Keyboard
- [ ] Keyboard backlight
- [x] Trackpad
- [x] Function keys
- [x] Wi-Fi
- [ ] Bluetooth
- [x] Camera
- [x] Sound
  
### Software

- [ ] AirDrop
- [x] iMessage
- [x] FaceTime
- [ ] Unlock with Apple Watch
- [x] QE/CI graphics acceleration
- [x] Metal support
- [X] Temperature sensors
- [x] Sleep / Wake
- [x] RTC (protection)
- [x] Hyperthreading
- [ ] Virtualisation (not tested)
  
<br>

***

## Problems

> [!CAUTION]
><ul>
><li><b>Internal Display (eDP) detected but displaying black</b></li>
> Despite me trying to find correct framebuffer patches, replacing SSDT's, and adding/deleting .kext's, I'm yet to fix the internal display. I have not been fruitful on my attempts, despite trying to fix the issue with multiple people, who have been longer in the hackintoshing game longer than I have. Please, if you have ANY information on how to fix this issue, leave it in issues. 


<li><b>ANOTHER PROBLEM HERE</b></li>
DESCRIBE YOUR PROBLEM HERE

<br><br>

<li><b><s>FIXED PROBLEM EXAMPLE</s> ‏‏‎ ‏‏‎ ‎‎‏‏‎ ‎ 🎉 FIXED!</b></li>
THE ART OF FIXING A PROBLEM AS DESCRIBED HERE

<br>

> [!TIP]
> Describe to viewers how you managed to fix the issue here.

</ul>

***

## System

The specs of the main system that the OpenCore configuration targets.

| **Motherboard** |                  MOTHERBOARD_MODEL                 |
|-----------------|:--------------------------------------------------:|
| **CPU**         |                      Intel i7-7500U                |
| **Chipset**     |             Intel SR2ZV (to check)                 |
| **Generation**  |                           Kaby Lake                |
| **Memory**      |                       16GB DIMM, manufacturer unknown   |
| **GPU**         | Intel HD Graphics 620                              |
| **NIC**         |                                      |
> [!IMPORTANT] i forgor

***

## ACPI

SSDTs used:
- SSDT-1
- SSDT-2
- SSDT-3
  
>todo: replace
***

## DeviceProperties

The following tables display the added PCI devices and their child keys.


### PciRoot(0x0)/Pci(0x2,0x0)

| **Key**                  | **Type** |   **Value**  |
|--------------------------|:--------:|:------------:|
| AAPL,ig-platform-id      |   Data   | ``00001659`` |
| device-id                |   Data   | ``16590000`` |
| framebuffer-fbmem        |   Data   | ``00009000`` |
| framebuffer-patch-enable |   Data   | ``01000000`` |
| framebuffer-stolenmem    |   Data   | ``00003001`` |
| framebuffer-unifiedmem   |   Data   | ``00000080`` |
| hda-gfx                  |  String  |   onboard-1  |

>todo: fill more info

<br>

### PciRoot(0x0)/Pci(0x1b,0x0)

Apple ALC

| **Key**                  | **Type** |   **Value**  |
|--------------------------|:--------:|:------------:|
| AAPL,ig-platform-id      |   Data   | ``0300220D`` |
| layout-id                |   Data   | ``01000000`` |

>todo: replace with that generic sunrise controller data. maybe this is why bluetooth not working


***

## Kernel

The following shows the kernel configuration.

### Kexts

Kexts used:
- Lilu
- WhateverGreen
- ...


### Patches

EXAMPLE

| **Key**     | **Type** |                **Value**                |
|-------------|:--------:|:---------------------------------------:|
| Arch        |  String  |                   Any                   |
| Base        |  String  |    __Z18e1000_set_mac_typeP8e1000_hw    |
| Comment     |  String  |               I225-V patch              |
| Count       |  Number  |                    1                    |
| Enabled     |  Boolean |                   True                  |
| Find        |   Data   |               ``F2150000``              |
| Identifier  |  String  | com.apple.driver.AppleIntelI210Ethernet |
| Limit       |  Number  |                    0                    |
| Mask        |   Data   |                                         |
| MaxKernel   |  String  |                  20.4.0                 |
| MinKernel   |  String  |                  19.0.0                 |
| Replace     |   Data   |               ``F3150000``              |
| ReplaceMask |   Data   |                                         |
| Skip        |  Number  |                    0                    |

>todo: remove, unness.

***

## Security

**SecureBootModel 》** SECURE_BOOT_MODEL

**Vault 》** Optional
>I don't think I need this one

***

## NVRAM

Contents stored in NVRAM.

<br>

### 4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14

| **Key**                | **Type** |   **Value**  |
|------------------------|:--------:|:------------:|
| DefaultBackgroundColor |   Data   | ``00000000`` |

>todo: remove from readme, unnessecary.

<br>

### 4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102

| **Key**       | **Type** | **Value** |
|---------------|:--------:|:---------:|
| rtc-blacklist |   Data   |           |

>remove this too? like what the fuck am I gonna block, my virginity?

<br>

### 7C436110-AB2A-4BBB-A880-FE41995C9F82

| **Key**                   | **Type** |                                    **Value**                                   |
|---------------------------|:--------:|:------------------------------------------------------------------------------:|
| boot-args                 |  String  | BOOT_ARGS |

***

## SMBIOS

### MAC_MODEL

This laptop is operating off a `MacbookPro14,1` SMBIOS, which, after a bit of Googling ~~and a very cursed CAPTCHA~~, will end you up with a Mid-2017 Macbook Pro with 4 Thunderbolt 3 ports. Unfortunately, this laptop has three USB-C holes, but this is the closest specced laptop, even though Apple *has* officially supported this CPU. This SMBIOS CPU is a 2.5 GHz Core i7 (i7-7660U). This has also been tested to work fine with `MacbookPro14,3` SMBIOS.

> todo: try other SMBIOS, MBP14,2, MBP15,1 and actually fucking figure out if this Intel CPU was supported by Apple

***



## UEFI

Drivers in use:

- OpenRuntime (obviously)
- ...
  
***

## Gallery

ADD SOME IMAGES TO SHOW OFF YOUR WORK!

<img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/9dd5dda0-92c3-4cc7-a7e4-3aab714671db" width="30%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/4694291b-adcd-4847-99e2-a4f89c9c1ac9" width="60%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/569407bd-0893-4974-82f0-ff669d317783" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/c3ec115d-fe2c-4382-9fa3-d73d3c10cfd2" width="45%"></img> 

>todo: I have some pics, just need some more

***

## Disclaimer

ADD A DISCLAIMER HERE!

***

## Greets

- @Coopydood - thanks for getting me in this "hobby" of mine, thanks for this template, thanks for everything. Owing you a beer. And a russian dictionary.

