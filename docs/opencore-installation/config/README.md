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

#### **ACPI**

#### **Kernel**

**Patches (Adding AMD Kernel Patches)**

1. Open patches.plist with ProperTree by pressing Ctrl-O \(Windows\) or Cmd-D \(MacOS\) in the current ProperTree window.
2. In the new patches.plist window, click on Patch and press Ctrl-C \(Windows\) or Cmd-C \(MacOS\) to copy the patches
3. Go back to the OC config window and **DELETE** Kernel/Patch section by pressing -
4. Press on Kernel in the first window and press Ctrl-V \(Windows\) or Cmd-V \(MacOS\) to paste the patches in your config.

**Quirks**

- ***DummyPowerManagement***: `True`
    - Alternative of NullCPUPowerManagement
    - You MUST need this
- *ExternalDiskIcon*: `True`
    - `True` to fix internal disk showing as external disk bug
- *PanicNoKextDump*: `True`
    - `True` to disable kext dumping in panic log which allow us to read the main panic log
- *PowerTimeoutKernelPanic*: `True`
    - `True` to help fixing kernel panics relating to power changes with Apple drivers in macOS Catalina, most notably with digital audio
- *XhciPortLimit*
    - `True` to fix stop sign while booting and `False` if you do not have this issue
    - For patching the 15-port-limit in macOS. Not recommend to enable but you may need this while installing
    - Remember to map USB after installation

#### **Misc**

**Boot**
- *ShowPicker*: `True`
    -  `True` to show the OpenCore picker
- *Timeout*: `0`
    - `0` to disable the timeout function meaning no auto boot
    - This sets how long OpenCore wait to boot to the default section. Measured in seconds

**Security**
- ***RequireVault***: `False`
    - `False` to disable Vault
- *ScanPolicy*: `0`
    - `0` to show all bootable device in OC Boot list

#### **NVRAM**

**Add**
- *7C436110-AB2A-4BBB-A880-FE41995C9F82*
    - *boot-args*: `-v keepsyms=1 npci=0x2000`
        - `-v` to show all the 'behind the scene' texts while booting
        - `debug=0x100` to prevent system from rebooting when it panics
        - `keepsyms=1` to print out symbols on a kernel panic
        - `npci=0x2000` to fix booting stuck at \[PCI Start Configuration\] or half printed text. **No need if you have Above 4G Decoding enabled in Bios**
    - ***csr-active-config***: `00000000`
        - `00000000` to enabled SIP completely. Recommended
        - `30000000` to allow unsigned kexts and writing to protected fs locations
        - `E7030000` to disable SIP completely
    - *nvda-drv*: `31`
        - `31` to enable NVidia Graphics Driver. Delete or empty this key if you don't have an NVidia GPU \(or Kepler GPU\)
    - *prev-lang:kbd*: `656E2D55 533A30`
        - `656E2D55 533A30` to set the language and the keyboard layout of the installer to English and QWERTY
        - If you want to choose language after booting to the installer, delete this key
        - For other languages, check out [this](https://github.com/acidanthera/OcSupportPkg/blob/master/Utilities/AppleKeyboardLayouts/AppleKeyboardLayouts.txt) for all languages and keyboard layouts

**WriteFlash**: `True`

#### UEFI

**Input**
- *PointerSupportMode*: blank
    - Specifies OEM protocol, currently only supports Z87 and Z97 ASUS boards so leave blank

**Proctools**
- *ConsoleControl*: `True`
    - `True` to replaces Console Control protocol with a builtin version, set to YES otherwise you may see text output during booting instead of nice Apple logo. Required for most APTIO firmware

**Quirks**
- ***ProvideConsoleGop***: `True`
    - `True` to enables GOP(Graphics output Protcol) which the macOS bootloader requires for console handle, required for seeing once the kernel takes over
    - This usually fix blackscreen after selecting boot option


<!-- tabs:end -->

<a href="#" onclick="window.history.back()">Go back</a>