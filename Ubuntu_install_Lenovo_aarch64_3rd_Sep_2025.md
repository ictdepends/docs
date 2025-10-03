# Ubuntu_install_Lenovo_aarch64_3rd_Sep_2025.md

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

Selct Start









---

Open BalenaEtcher. - works on both Windows and Linux and it is an easy and stright forward solution.

Click on 'Flash from file', select ubuntu-25.04-live-server-arm64.iso from File Explorer, click open.

Click 'Select target' on balenaEtcher. Select1 D:,E: will get override into one by balena.

Flash!

When done - safely remove USB.

## Install
Perfect — now you’ve got **Ubuntu 25.04 on your USB stick** 🎉
Now let’s get it installed properly next to Windows without breaking anything.

---

## 🔹 What you do next

1. **Reboot your laptop** with the USB plugged in.

   * While it’s starting, press **F12** (on Lenovo) to open the **boot menu**.
   * Select your **USB device**.

2. **Start the Ubuntu installer**

   * Choose **Install Ubuntu** (not Try Ubuntu).

3. **When it asks about installation type**:

   * Do **not** choose *Erase disk*.
   * Instead choose **Something else**.

4. **Find your old Ubuntu partition**

   * You’ll see a list of partitions.
   * Windows ones are usually **NTFS** or marked EFI → ❌ don’t touch them.
   * Old Ubuntu is usually **ext4** (and maybe a swap).

5. **Replace the old Ubuntu partition**

   * Highlight the old **ext4** partition.
   * Click **Change** → set:

     * **Use as:** `Ext4 journaling file system`
     * **Mount point:** `/`
     * **Format?** ✅ Yes (so it clears the old broken Ubuntu).

6. **Install the bootloader**

   * Make sure it’s set to install GRUB into the **EFI partition** (Ubuntu should detect it automatically).
   * This ensures you’ll get a menu at startup with both **Windows** and **Ubuntu**.

7. **Proceed with installation**

   * Ubuntu will now install fresh into that old partition.
   * Windows partitions remain untouched.

---

## 🔹 After installation

* On reboot, you’ll see the **GRUB menu** → choose Ubuntu or Windows.
* If Ubuntu ever stops booting, you can always use the USB again to repair.
* Keeping this USB around = your **recovery tool**.

---

👉 Since your machine is Snapdragon X Elite (ARM), you picked **Ubuntu 25.04** → ✅ good choice for better hardware support.

Do you want me to show you **exactly how the partitions will look in the installer** (so you can easily recognize which one is old Ubuntu and which one is Windows)?

---

If I see only on F12 pushed repeatedly:
"Please select boot device: 

ubuntu (S77LNFWC25018-SAMSUNG MZAL81T0HDLB-00BL2)

Windows Boot Manager (S77LNF1WC25018-SAMSUNG MZAL81T0HDL...)"

Then restart pushing F2 repatedly to see boot(no FN needed).
Check in Boot on left hand side that USB boot is enabled.

Conclusion - do not use balenEtcher, use Rufus as it gives more control.









