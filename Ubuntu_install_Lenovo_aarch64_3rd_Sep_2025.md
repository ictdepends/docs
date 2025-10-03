# Ubuntu_install_Lenovo_aarch64_3rd_Sep_2025.mdwas still version 25

Error on prevuious Ubuntu installation, : Ubuntu boot failed.

First download 'Ubuntu Server', as there isn't yet an official Desktop for Snapdragon X Elite laptops.

After installation, log in and run:
```bash
sudo apt update
sudo apt upgrade -y
sudo apt install ubuntu-desktop -y
```
## Download
https://ubuntu.com/download/server/arm

Downloaded 25.04 as it is best for my modern pc, LTS version may not work correctly.

Insert flash drive into machine, it reads a E.

Conclusion from previous install - do not use balenEtcher, use Rufus as it gives more control.

### Rufus
Boot selection:UEFI:NTFS
Partition schome: GPT
Target system: UEFI(non CSM)
File System NTFS

Select Start

When you see Ready in green close rufus and safely eject usb.

Ignore below warning if you see it.
"Problem ejecting Mass Storage Device warnig: Windows can't stop 'Volume' device because a program is still using it, Close any programms that might be using the device, and then try again later."

insert USB restart computer pressing on pulsations F12 (no fn). You see EFI USB Device (Samsung Type_C).

---
Ah — got it. I remember now: you said Rufus **only offers NTFS or exFAT**, not FAT32, because the Ubuntu 25.04 ISO is bigger than 4 GB. ✅

That’s an important constraint. So we can **ignore FAT32** — the USB must be NTFS (Rufus handles UEFI:NTFS boot automatically).

This narrows the problem: your USB is **UEFI:NTFS**, which usually works, but your Lenovo firmware is **failing to boot it**. So the systematic troubleshooting can focus on **firmware/BIOS and internal factors**, not the USB format.

---

### Refined systematic approach given NTFS USB

1. **USB verification**

   * Rufus says “Ready” → USB creation OK
   * Optional: test USB on another PC (to confirm it boots)

2. **BIOS / UEFI check**

   * USB Boot: Enabled
   * Fast Boot: Disabled
   * Secure Boot: Try temporarily disabling if boot fails
   * Use **Fn + F12** to access boot menu immediately after power-on

3. **USB port**

   * Prefer **USB-A** or direct ports — some USB-C ports are picky with UEFI:NTFS

4. **BitLocker / encryption check**

   * Suspend BitLocker on Windows system drive → retry USB boot

5. **Boot attempt / error capture**

   * Note exact EFI failure message
   * If EFI boot fails consistently → firmware incompatibility with NTFS USB is likely

---

💡 At this point, if USB won’t boot with NTFS on Lenovo:

* Either use a **different USB stick** (some sticks are firmware picky), **or**
* Use **Ventoy** or another tool that splits large ISOs for FAT32 automatically, making it compatible with all Lenovo UEFI firmwares.

---

If you want, I can give you a **step-by-step method using Ventoy or Rufus to make a guaranteed bootable Ubuntu 25.04 USB for Lenovo X1**, **without needing FAT32**, so it will always appear and boot.

Do you want me to do that?

---





