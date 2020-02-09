# 來吧！

!> _**請謹慎閱讀以下內容**_

# 一般準備

### 基本

* **至少 4GB 的 USB（在線）或 8GB 的 USB（離線）**
* 你的電腦需要的 Kexts（內核擴展）\([準備 Kexts](gathering-kexts.md)\)
* [gibMacOS](https://github.com/corpnewt/gibMacOS) 的 Clone（克隆）
* [**PYTHON 3**](https://www.python.org/downloads/)

### **四葉草引導的 Config.plist（設定檔）**

* **請到這裡** [**HERE**](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/config.plist-basics) **閱讀 Plist 基本，然後用 Clover Configurator 或 Clover Cloud Editor 或 ProperTree （由國外大神 CorpNewt 製作）製作自己的 config.plist**
  * _**請勿使用樣本 config**_
* **閱讀完後，到**[**這裡**](../amd-clover-config.plist/)**製作自己的 config**
* [**AptioMemoryFix.efi**](https://cdn.discordapp.com/attachments/251043252046659586/609234258732515329/AptioFix-R27-RELEASE.zip) **\(Clover 自帶的版本可能會有問題\)**

### 建議

如果你是在 Windows 中製作安裝器的話，我建議你使用線上安裝

如果你是在 macOS 中製作安裝器的話，我建議你使用離線安裝

# 線上安裝準備

!> 你需要 LAN \(乙太網路\) 連線。如果你沒有，請使用[**離線安裝**](offline-installer-prerequisites.md)

### 一般

* 網路速度**一定**最少要有 20 Mbps. 如果你的網路速度較慢，使用離線安裝因為在安裝期間可能會被鎖上

### 在 macOS 中製作安裝器

* [Clover install package](https://cloverdb.com)
  * 使用 r5092
* [Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/)
  * 在 macOS 編輯 config.plist

### 目前有問題 ~~在 Windows 中製作安裝器~~

* [Clover Cloud Editor](http://cloudclovereditor.altervista.org/cce/index.php)
  * 在 Windows 編輯 config.plist

# 離線安裝準備

### 一般

* 下載 [MakeInstallmacOS](https://github.com/doesprintfwork/MakeInstallmacOS)
* [**PYTHON 3.4 or above（推薦：3.7, 並選擇加到路徑 Path）**](https://www.python.org/downloads/)

### 在 macOS 中製作安裝器

* [Clover install package](https://cloverdb.com)
  * 使用最新的，請記得版本
* [Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/)
  * 在 macOS 編輯 config.plist

### 在 Windows 中製作安裝器

* [Clover Cloud Editor](http://cloudclovereditor.altervista.org/cce/index.php)
  * 在 Windows 編輯 config.plist
* [TransMac](https://www.acutesystems.com/scrtm.htm)
* [Paragon Hard Disk Manager](https://www.paragon-software.com/free/pm-express/#) -- 雖然這個程式可能會有嚴重的 Bug, 這是唯一一種方法在 Windows  中去調整 HFS+ 容器（如果你能找到更好的方法，告訴我！）
* [Boot Disk Utility](http://cvad-mac.narod.ru/index/bootdiskutility_exe/0-5) \(BDU\) -- 格式化硬碟
* **你需要** [**7-zip**](https://www.7-zip.org/)**（安裝到** `C:\Program Files (x86)\7zip`**）**

# 系統要求

* **AMD \(FX, Ryzen 或 Zen Athlon\) CPUs**
* **獨立顯示卡（GPU）**
* 如需一個顯示卡列表，請到 [**GPU Buyers Guide**](https://khronokernel-3.gitbook.io/catalina-gpu-buyers-guide/)\*\*\*\*
* 請記得你的**最高支援系統 \(Highest Supported OS\)**
* **由於我還沒有寫完 Legacy BIOS 的方法，你需要有 UEFI 的主機板**

!> **AMD 的內顯是不支持的！**

# 收集 Kexts

?> 請將所有已下載的 Kexts 放到一個資料夾內

### 你需要什麼 Kexts?

#### 我可以在哪裡找到這些 Kexts?

* 所有在此顯示的 Kexts（除 SmallTreeIntel82576 以外）都可從由 Goldfish64 提供以及維護的 [_**Kext Repo**_](https://kext.goldfish64.com) _**取得**_
* _**不要**_ **下載並使用所有 Kexts （可能會導致內核崩潰 Kernel Panic）**

#### **什麼是必需的？**

[**VirtualSMC.kext**](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455091&cid=FE4038DA929BFB23) _\(使用這個\)_ 或 [FakeSMC.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455161&cid=FE4038DA929BFB23) \(較舊，會在 FAQ 中提到\) 這個 kext 告訴 macOS "對這是一台真的 Mac", 模擬在真 Mac 上 SMC 的功能。如果沒有了它，便沒有黑蘋果。**不要同時使兩個 SMC kexts.**

**你亦需要這些**

* [_Lilu.kext_](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455053&cid=FE4038DA929BFB23) _-_ 這個 Kext 就像其它 Kexts 的載入器
* [_Whatevergreen.kext_ ](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455095&cid=FE4038DA929BFB23)_-_ 這個 Kext 可修複許多 GPU 的問
* [_NullCPUPowerManagement.kext_](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455158&cid=FE4038DA929BFB23) **- This kext disables CPU power management,** _**as that is not supported on AMD chips.**_

#### 乙太網路（選你需要的）

* [_IntelMausiEthernet.kext_](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455134&cid=FE4038DA929BFB23) - 大部分新的 Intel 乙太網路卡 **除 I122-AT 外**
* [_AppleIntelE1000e.kext_](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455998&cid=FE4038DA929BFB23) - 比較舊的 Intel 乙太網路卡 - 但可能會在新的卡上導致內核崩潰
* [_AtherosE2200Ethernet.kext_](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455105&cid=FE4038DA929BFB23) - 大部份的 Atheros 和 Killer 乙太網路卡
* [_RealtekRTL8111.kext_](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455143&cid=FE4038DA929BFB23) - 大部份 Realtek Gigabit 乙太網路卡
* [_RealtekRTL8100.kext_](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455140&cid=FE4038DA929BFB23) - Realtek 10/100 mbps 乙太網路卡
* [_SmallTreeIntel82576.kext_](https://drive.google.com/file/d/0B5Txx3pb7pgcOG5lSEF2VzFySWM/view) - **Intel I122-AT 乙太網路卡**

#### USB Tethering（USB 繫連）

* [_HoRNDIS.kext_](https://github.com/midi1996/JBOG/blob/master/Extra/HoRNDIS.kext.zip?raw=true) - For USB tethering from Android **only**.

#### WiFi and Bluetooth 

\(我並沒有任何對這方面的知識，以下引用自 CorpNewt 的 Intel Vanilla Guide\) 

> Apple is pretty minimal with their WiFi support, so I'll only cover the two main chipsets I'm familiar with. I've used a BCM94360CD + PCIe adapter, and BCM94352HMB/BCM94352Z in my Hackintoshes. The BCM94360CD worked OOB with no extras as it's a native card. For the BCM94352 flavors, I've been using [AirportBrcmFixup.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455063&cid=FE4038DA929BFB23) and the companion [Lilu.kext](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455053&cid=FE4038DA929BFB23) for WiFi setup and BrcmBluetoothInjector.kext \(on 10.13.6+\) or_BrcmPatchRAM2.kext_ alongside BrcmFirmwareData.kext - all of the Brcm\* kexts are from RehabMan's [OS-X-BrcmPatchRAM](https://github.com/RehabMan/OS-X-BrcmPatchRAM) repo.

#### 音頻（只需一個）

* [_AppleALC.kext_](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455056&cid=FE4038DA929BFB23) _-_ 支持市面上大部分的 codec 有最好的音質**但只支持 Ryzen**
  * **不支持 FX**
  * **Ryzen 會失去 3.5mm 麥克風的支持**
* [_VoodooHDA.kext_ ](https://sourceforge.net/projects/voodoohda/)_-_ 萬用的音頻 Kext
  * **支持 FX**
  * **支持麥克風**
  * **較差音質**

### 源碼連結

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
