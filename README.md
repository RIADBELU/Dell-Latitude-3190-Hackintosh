# Dell-Latitude-3190-Hackintosh
I've managed to get OpenCore and Hackintosh working on the Dell Latitude 3190 2-in-1 Laptop.
Please note that if there are some glitches, bugs, or anything. Please report them to me.
Any files or the config.plist may subject to change in the future.
The system if booted into macOS will be recognised as a MacBookAir7,1.
The maximum macOS it can support is macOS 12 Monterey, if possible, you can try macOS 26 Tahoe.
Follow the Dortania's OpenCore guide in order to download the macOS Recovery files (you'll need Python installed on your computer).
For the tech savvys out there, i've also included a "Reset NVRAM" entry in the OpenCore boot menu for advnced diagnosis.
If you try newer macOSes, you wont be able to properly use the operating system.
TRY THIS AT YOUR OWN RISK.. I recommend using an external SSD to easily get back into your current OS.
KEEP IN MIND THAT THIS IS AN UNOFFICIAL OPENCORE EFI PREBUILD. I AM NOT AFFILIATED WITH OPENCORE OR HACKINTOSH...
Below here is going to be a guide to install the Hackintosh.
But, you'll need to know the materials, so, here's the materials needed.

## Materials

- 🛠️ [EFI Folder](./EFI) — Main EFI files for Hackintosh installation
- 📚 [Docs](./docs) — Guides, troubleshooting, and documentation
- 📦 [Kexts](./Kexts) — Essential kexts for this model
- 📝 [config.plist](./EFI/OC/config.plist) — OpenCore configuration file

---

## Things To Look At Beforehand

- 🖥️ [Screenshots](./screenshots) — Visual results and BIOS settings
- ❗ [Known Issues](./docs/known-issues.md) — List of current limitations or bugs
- ✅ [Compatibility List](./docs/compatibility.md) — What works and what doesn’t
- 🤝 [Contributing Guide](./CONTRIBUTING.md)
- 📄 [License](./LICENSE)

---

# Guide
Over here, we'll list 2 ways to install the Hackintosh, the Internal Drive way and the External Drive way. It will take a little while depending on your internet and hard drive speed. So, please stay patient during the initial process. And this is for Windows users only. Alright, Let's move on, and I'll walk you through the steps! 

---

## Internal Drive Way
We'll show you 2 ways here. The Normal way and The Dual Boot way. First, let's start off with the normal way.

---

### The Normal Way
---
#### ⚠️WARNING⚠️
This method will overwrite your current operating system with macOS and all data and old history will be lost! If you do not wish to continue, either skip this step or don't do this at all!

---

1.) Prepare a USB with at least 8-16GB with the nessecary files (e.g. com.apple.recovery.boot, and the EFI folder)

2.) Restart your Dell Latitude 3190, then head into BIOS

3.) Do this in the BIOS:

- Disable Secure Boot
- Switch from SATA to AHCI
- Set OpenCore as the first boot priority
- Set your USB as the second boot priority

4.) Save your changes and exit the BIOS.

5.) Once you're in OpenCore, select "macOS Recovery"

6.) Once you're in reovery, head over to Disk Utility

7.) Click "Show All Disks"

8.) Head over to the disk and erase it.

9.) At the Erase Disk screen, do this:
 
- Name: macOS (or Macintosh HD)
- Format: APFS
- Scheme: GPT (GUID Partition Table)

10.) After that, head over to "Install macOS [codename] (alternatively, "Reinstall macOS [codename])

11.) Install macOS to [your-hard-drive-name] disk

12.) Wait patiently after Step 11, your computer will reboot several times (each time, just select "macOS Installer", but if you see [your-hard-drive-name]-Data, select that)

13.) When you see the setup screen, set up your device the way you like it.

14.) When you get to the desktop, mount your EFI partition (via MountEFI)

15.) After that's done, copy your BOOT and OC file from your EFI file in your USB to your EFI partition in your hard drive

16.) That's it! Enjoy! If nessecary, install the drivers for the Dell Latitude 3190

---

### The Dual Boot Way
---

1.) Open Disk Management by pressing ⊞ + X, then by selecting Disk Management

2.) Split the Windows partition equally, then set up the partition with these attributes:

- Name: macOS
- Size: [close-to-the-maximum-size] (Leave at least 2-4 GB)
- Format: FAT32
- Allocation size (if asked): Default

3.) Then, get and prepare a USB with at least 8-16GB with the nessecary files (e.g. com.apple.recovery.boot, and the EFI folder)

4.) Restart your Dell Latitude 3190, then head into BIOS

5.) Do this in the BIOS:

- Disable Secure Boot
- Switch from SATA to AHCI
- Set OpenCore as the first boot priority
- Set your USB as the second boot priority

6.) Save your changes and exit the BIOS.

7.) Once you're in OpenCore, select "macOS Recovery"

8.) Once you're in reovery, head over to Disk Utility

9.) Click "Show All Disks"

10.) Head over to the disk and erase it.

11.) At the Erase Disk screen, do this:
 
- Name: macOS (or Macintosh HD)
- Format: APFS
- Scheme: GPT (GUID Partition Table)

12.) After that, head over to "Install macOS [codename] (alternatively, "Reinstall macOS [codename])

13.) Install macOS to [your-hard-drive-name] disk

14.) Wait patiently after Step 11, your computer will reboot several times (each time, just select "macOS Installer", but if you see [your-hard-drive-name]-Data, select that)

15.) When you see the setup screen, set up your device the way you like it. 

16.) That's it! Enjoy! If nessecary, install the drivers for the Dell Latitude 3190

---

## External Drive Way
---

1.) Open Disk Management by pressing ⊞ + X, then by selecting Disk Management

2.) Split the hard drive equally, then set up one of the partitions with these attributes:

- Name: macOS
- Size: [close-to-the-maximum-size] (leave 2-4 GB)
- Format: exFAT
- Allocation size (if asked for): Default

3.) Use the other space to make a new partition, using these attributes:

- Name: EFI
- Size: 2-4 GB
- Format: FAT32
- Allocation size (if asked for): Default

3.) Then, get and prepare the EFI folder with the nessecary files (e.g. com.apple.recovery.boot, and the EFI folder)

4.) Restart your Dell Latitude 3190, then head into BIOS

5.) Do this in the BIOS:

- Disable Secure Boot
- Switch from SATA to AHCI
- Set OpenCore as the first boot priority
- Set your hard drive as the second boot priority

6.) Save your changes and exit the BIOS.

7.) Once you're in OpenCore, select "macOS Recovery"

8.) Once you're in reovery, head over to Disk Utility

9.) Click "Show All Disks"

10.) Head over to the macOS disk and erase it.

11.) At the Erase Disk screen, do this:
 
- Name: macOS (or Macintosh HD)
- Format: APFS
- Scheme: GPT (GUID Partition Table)

12.) After that, head over to "Install macOS [codename] (alternatively, "Reinstall macOS [codename])

13.) Install macOS to [your-hard-drive-name] disk

14.) Wait patiently after Step 11, your computer will reboot several times (each time, just select "macOS Installer", but if you see [your-hard-drive-name]-Data, select that)

15.) When you see the setup screen, set up your device the way you like it. 

16.) That's it! Enjoy! If nessecary, install the drivers for the Dell Latitude 3190
