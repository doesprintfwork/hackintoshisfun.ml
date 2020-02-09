# AMD OpenCore config.plist

## Before anything

* Please get the patches.plist from the downloaded AMD_Vanilla Repo folder. \(17h for Ryzen, 15h and 16h for FX\)

## Start!

1. Copy the `Sample.plist` in `OpenCore release folder/Docs` to desktop and rename it to `config.plist`
1. Open ProperTree plist editor
2. Press Ctrl-O \(Windows\) or Cmd-O \(MacOS\)
3. Open the `config.plist` that you have just renamed
2. Press Ctrl-R \(Windows\) or Cmd-R \(MacOS\)
3. Choose the OC folder you have setup
4. At this point, the ProperTree editor will auto fill in the OC config for your hardware. But we still need to manually change some settings and add the AMD kernel patches

<!-- tabs:start -->

#### **Kernel**

**Patches (Adding AMD Kernel Patches)**

1. Open patches.plist with ProperTree by pressing Ctrl-O \(Windows\) or Cmd-D \(MacOS\) in the current ProperTree window.
2. In the new patches.plist window, click on Patch and press Ctrl-C \(Windows\) or Cmd-C \(MacOS\) to copy the patches
3. Go back to the OC config window and **DELETE** Kernel/Patch section by pressing -
4. Press on Kernel in the first window and press Ctrl-V \(Windows\) or Cmd-V \(MacOS\) to paste the patches in your config.

**Quirks**

- *XhciPortLimit*
    - `True` to fix stop sign while booting and `False` if you do not have this issue

#### **Misc**

**Boot**
- *ShowPicker*: `True`
    -  `True` to show the OpenCore picker
- *Timeout*: `0`
    - `0` to disable the timeout function meaning no auto boot

**Security**
- *RequireVault*: `False`
    - `False` to disable Vault
- *ScanPolicy*: `0`
    - `0` to show all bootable device in OC Boot list

#### **NVRAM**

**Add**
- *7C436110-AB2A-4BBB-A880-FE41995C9F82*
    - *boot-args*: `-v keepsyms=1`
        - `-v` to show all the 'behind the scene' texts while booting
        - `keepsyms=1` to prevent system from rebooting when it panics
    - *csr-active-config*: `E7030000`
        - `E7030000` to disable SIP which is unsupported on AMD CPUs. Though, you can test it after you have install macOS. Google for other value
    - *nvda-drv*: `31`
        - `31` to enable NVidia Graphics Driver. Delete this key if you don't have an NVidia GPU \(or Kepler GPU\)
    - *prev-lang:kbd*: `656E2D55 533A30`
        - `656E2D55 533A30` to set the language and the keyboard layout of the installer to English and QWERTY

<!-- tabs:end -->
