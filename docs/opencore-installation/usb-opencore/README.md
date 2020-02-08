# Configuring OpenCore in Windows

1. Open `BOOT` volume and go into `EFI/OC`. 
2. Make a config with [this page](../config/) and place it in `EFI/OC`
2. After that, put all the kexts you have downloaded \(in [Gathering Kexts page](../../prerequisites/get-started/README#gathering-kexts)\) to `EFI/OC/Kexts` folder. **Skip all of the SMC kexts** \(except VirtualSMC.kext and FakeSMC.kext\) as they might cause Kernel Panic\(s\).
3. Go back to `EFI/OC` and go into `Drivers`
4. Delete all files except for `FwRuntimeServices.efi`
5. Copy `ApfsDriverLoader.efi` and `VBoxHfs.efi` from `AppleSupportPkg` to `EFI/OC/Drivers` folder
6. Yay! You are ready to [install macOS](../../actual-installation/actual-installation-part-1.md)!🥳

# Install and Configuring OpenCore in macOS

1. Mount EFI of your USB
2. Copy the OC folder to EFI
2. Make a config with [this page](../config/) and place it inside `EFI/OC`
4. Put all the kexts you have downloaded \(in [Gathering Kexts page](../../prerequisites/get-started/README#gathering-kexts)\) to `EFI/OC/Kexts` folder
5. Delete all files except for `FwRuntimeServices.efi`
6. Copy `ApfsDriverLoader.efi` and `VBoxHfs.efi` from `AppleSupportPkg` to `EFI/OC/Drivers` folder
7. You have finally made the installer! You can proceed to [install macOS](../../actual-installation/actual-installation-part-1.md)! Yay! 🥳 
