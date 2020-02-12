# Prerequisites


!> _**Please READ everything CAREFULLY!**_

# General Prerequisites

* An 8GB+ USB flash drive for the installer
* Kexts for your system \([Gathering Kexts](gathering-kexts.md)\)
* A clone of [gibMacOS](https://github.com/corpnewt/gibMacOS)
* [**PYTHON 3** or above \(Recommended: 3.7, with add to PATH selected\)](https://www.python.org/downloads/)
* [AppleSupportPkg](https://github.com/acidanthera/applesupportpkg/releases)
- **CLOVER**
    * [Clover Cloud Editor](http://cloudclovereditor.altervista.org/cce/index.php)
- **OPENCORE**
    - [ProperTree Editor](https://github.com/corpnewt/ProperTree)

# WAIT

### So which boot-loader should I choose for macOS?

If you want to have the latest macOS not long after it released, use OpenCore. In other words, Clover is already way tooooooooooo outdated.

### Then, why would I still talk about Clover?

Installing with Clover would still be a little bit easier and you can setup OpenCore in macOS much easier if you have the basis of Clover.

---

# Network Installer Prerequisite

You'll need to have **LAN \(Ethernet\) connection** if you are making a **Network Installer**. If you do _**NOT**_ have it, please make an [**Offline Installer**](#offline-installer-prerequisites.md) instead.

### The only prerequisite
* You **MUST** have fast Internet Speed \(at least 20 Mbps\). If your Internet Speed is slow, make an Offline Installer instead as the Installer could be locked while installing.

---

# Offline Installer Prerequisites

### General

* A clone of [MakeInstallmacOS](https://github.com/doesprintfwork/MakeInstallmacOS)
* **\[OPTIONAL\]** Fast Internet Speed
* [PYTHON 3.4 or above \(Recommended: 3.7, with add to PATH selected\)](https://www.python.org/downloads/)

### Preparation for making an Offline Installer from macOS

- **CLOVER**
    * [Clover install package](https://github.com/Dids/clover-builder/releases) \(Get the latest .pkg file and remember the version\)
- **OPENCORE**
    - [OpenCore latest release package](https://github.com/acidanthera/OpenCorePkg/releases)

### Preparation for making an Offline installer in Windows

* [TransMac](https://www.acutesystems.com/scrtm.htm)
* [Paragon Hard Disk Manager](https://www.paragon-software.com/free/pm-express/#) -- Although there are some issues, it is the only way we can resize an HFS+ Volume in Windows \(if you can find any better ways, tell me!\)
* [Boot Disk Utility](http://cvad-mac.narod.ru/index/bootdiskutility_exe/0-5) \(BDU\) -- For formatting disk and restoring files
* **You'll need** [7-zip](https://www.7-zip.org/) **\(installed to** `C:\Program Files (x86)\7zip`**\)** for the Scripts you'll use later.
- **CLOVER**
    - Nothing
- **OPENCORE**
    - [OpenCore latest release package](https://github.com/acidanthera/OpenCorePkg/releases)

---

# Requirements

* **AMD \(FX, Ryzen or Zen Athlon\) CPUs**
* **A dedicated GPU**
* _**Remember that the iGPU of AMD CPUs is not supported.**_
* For a complete list of supported GPUs, please refer to the [**GPU Buyers Guide**](https://khronokernel-3.gitbook.io/catalina-gpu-buyers-guide/) **and** _**remember your Highest Supported OS.**_

---

# Gathering Kexts

?> **Please keep all of the downloaded kexts to a folder. We will need them later**

### What Kexts Do You Need?

#### Where can I find these kexts?

All the kexts shown here \(except SmallTreeIntel82576\) are available for download on the [kext repo](https://1drv.ms/f/s!AiP7m5LaOED-m-J8-MLJGnOgAqnjGw) provided and maintained by Goldfish64. **Do** _**NOT**_ **download and use all of the kexts listed below. Doing this may result a kernel panic.**

#### **What is absolutely required?**

[VirtualSMC.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455091&cid=FE4038DA929BFB23) _\(use this\)_ or [FakeSMC.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455161&cid=FE4038DA929BFB23) \(older, if VirtualSMC doesn't work, use this instead\) is as aforementioned essential. This kext is what tells macOS "Yes this is a real Mac", emulating the functionality of the SMC on real Mac's. Without it, no Hackintosh. **Do NOT use both of the SMC kexts.**

**You'll need these also**

* [Lilu.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455053&cid=FE4038DA929BFB23) _-_ this kext acts as a loader for other kexts. More specifically it can patch kexts, processes and libraries.
* [Whatevergreen.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455095&cid=FE4038DA929BFB23)_-_ this kext fixes a lot of GPU related issues.

?> ***For Clover ONLY:***<br />[NullCPUPowerManagement.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455158&cid=FE4038DA929BFB23) **- This kext disables CPU power management,** _**as that is not supported on AMD chips.**_

#### Ethernet \(Choose the one you need\)

* [IntelMausiEthernet.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455134&cid=FE4038DA929BFB23) - this works with most newer Intel LAN chipsets **except I122-AT.**
* [AppleIntelE1000e.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455998&cid=FE4038DA929BFB23) - this works with older Intel LAN chipsets - but can cause kernel panics on newer chipsets
* [AtherosE2200Ethernet.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455105&cid=FE4038DA929BFB23) - this works for most Atheros or Killer networking chipsets
* [RealtekRTL8111.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455143&cid=FE4038DA929BFB23) - this works with most gigabit Realtek LAN chipsets
* [RealtekRTL8100.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455140&cid=FE4038DA929BFB23) - for 10/100 Realtek LAN chipsets
* [SmallTreeIntel82576.kext](https://drive.google.com/file/d/0B5Txx3pb7pgcOG5lSEF2VzFySWM/view) - **for Intel I122-AT LAN chipset** only.

#### USB Tethering

* [HoRNDIS.kext](https://github.com/midi1996/JBOG/blob/master/Extra/HoRNDIS.kext.zip?raw=true) - For USB tethering from Android **only**.

#### WiFi and Bluetooth 

\(I myself don't use bluetooth nor WiFi so I don't have knowledge in that, but here is some information on the subject by CorpNewt.\) 

> Apple is pretty minimal with their WiFi support, so I'll only cover the two main chipsets I'm familiar with. I've used a BCM94360CD + PCIe adapter, and BCM94352HMB/BCM94352Z in my Hackintoshes. The BCM94360CD worked OOB with no extras as it's a native card. For the BCM94352 flavors, I've been using [AirportBrcmFixup.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455063&cid=FE4038DA929BFB23) and the companion [Lilu.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455053&cid=FE4038DA929BFB23) for WiFi setup and _BrcmBluetoothInjector.kext_ \(on 10.13.6+\) or _BrcmPatchRAM2.kext_ alongside _BrcmFirmwareData.kext_ - all of the Brcm\* kexts are from RehabMan's [OS-X-BrcmPatchRAM](https://github.com/RehabMan/OS-X-BrcmPatchRAM) repo.

#### Audio \(Do not get both\)

* [AppleALC.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455056&cid=FE4038DA929BFB23) _-_ this kext supports most of the commonly used codecs, with the best quality. Ryzen CPUs are supported. **No FX support! Also, 3.5mm microphones are broken on Ryzen.**
* [VoodooHDA.kext ](https://sourceforge.net/projects/voodoohda/)_-_ a jack of all trades master of none solution to audio. **Required on FX. Mic support on Ryzen.**

#### Misc
* [XLNCUSBFix.kext](https://files.amd-osx.com/XLNCUSBFix.kext.zip) - may fix USB problems \(including Stop Sign\) on FX

### **Source Code Links**

* [VirtualSMC](https://github.com/acidanthera/VirtualSMC)
* [FakeSMC](https://github.com/RehabMan/OS-X-FakeSMC-kozlek)
* [Lilu](https://github.com/acidanthera/Lilu)
* [WhateverGreen](https://github.com/acidanthera/WhateverGreen)
* [IntelMausiEthernet](https://github.com/Mieze/IntelMausiEthernet)
* [AppleIntelE1000e](https://github.com/chris1111/AppleIntelE1000e)
* [AtherosE2200Ethernet](https://github.com/Mieze/AtherosE2200Ethernet)
* [RealtekRTL8111](https://github.com/Mieze/RTL8111_driver_for_OS_X)
* [RealtekRTL8100](https://github.com/Mieze/RealtekRTL8100)
* [AirportBrcmFixup](https://github.com/acidanthera/AirportBrcmFixup)
* [AppleALC](https://github.com/acidanthera/AppleALC)
* [NullCPUPowerManagement](https://github.com/corpnewt/NullCPUPowerManagement)
* [VoodooHDA](https://sourceforge.net/p/voodoohda/code/HEAD/tree/)

[**Next Page**](../../download/) to download the installer

<a href="#" onclick="window.history.back()">Go back</a>