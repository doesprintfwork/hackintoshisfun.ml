# <big>Clover Time!</big>

---

# Configuring Clover in Windows

## Part 1 - Config and Kexts

1. Once finished, you should be able to see a new partition called `CLOVER` is mounted. Open it and go into `EFI/CLOVER`. Replace the original one with the config.plist you've made.
2. After that, put all the kexts you have downloaded \(in [Gathering Kexts page](../../prerequisites/get-started/README#gathering-kexts)\) to `EFI/CLOVER/kexts/Other` folder. **Skip all of the SMC kexts** \(except VirtualSMC.kext and FakeSMC.kext\) as they might cause Kernel Panic\(s\).
3. And delete the FakeSMC.kext. \(if you are using VirtualSMC.kext\)

![Config and Kexts](../../_images/ezgif-4-106771fe2b5a.gif)

## Part 2 - Drivers

#### For UEFI:

1. Go back to `EFI/CLOVER` and go into `drivers/UEFI`
2. Delete everything **except**:
    - `ApfsDriverLoader.efi`
    - `AptioMemoryFix.efi`
    - `HFSPlus.efi`
3. Yay! You are ready to [install macOS](../../actual-installation/actual-installation-part-1.md)!🥳

# Install and Configuring Clover in macOS

1. Open the Clover installer.
2. Install it to your USB with these settings. \(Choose Customize in `Installation Type` part\)
    * **UEFI:** 
    ```
        Clover for UEFI booting only Install Clover in the ESP
        Recommended Drivers:
        - ApfsDriverLoader
        - AptioMemoryFix
        - HFSPlus
        Install RC Scripts on target volume (or Install RC Scripts on other volumes)
    ```
    More explanations [here](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/clover-setup).
3. When it is finished, a volume call EFI should be mounted. Replace the original config.plist in `EFI/EFI/CLOVER` with the config.plist you've made.
4. After that, put all the kexts you have downloaded \(in [Gathering Kexts page](../../prerequisites/get-started/README#gathering-kexts)\) to `EFI/EFI/CLOVER/kexts/Other` folder.
5. You have finally made the installer! You can proceed to the [next part](../../actual-installation/actual-installation-part-1.md)! Yay! 🥳 

![Steps 3 - 4 \(Copy files to Clover\)](../../_images/ezgif-4-7eed77270d16.gif)
