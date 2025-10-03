# Partitions1_Ubuntu_install_Lenovo_aarch64_3rd_Sep_2025

Got it 👍 You want to **dual boot Windows 11 + Ubuntu 25.04 ARM64** on your Yoga Slim (Snapdragon X Elite) and reuse/replace the old Ubuntu partition safely.

Let’s break this into two parts:

---

## 🔹 1. Understanding Partitions for Dual Boot

On your system you already have:

* **Windows partitions** (EFI, Recovery, C:, etc.) → don’t touch these.
* **Old Ubuntu partitions** (from your install 6 months ago).

During the Ubuntu installer:

1. Choose **Something else** (instead of “Erase disk”).

   * This gives you full control of partitions.
2. Find the old Ubuntu partition(s). Usually they look like:

   * **ext4** filesystem
   * maybe also a **swap** partition (not always needed anymore)
3. Select the old Ubuntu partition → click **Change** → set:

   * **Use as:** `Ext4 journaling file system`
   * **Mount point:** `/`
   * **Format?** ✅ Yes (this wipes the old Ubuntu and installs new one)

⚠️ **Do NOT format or touch EFI or Windows partitions**. Leave them as-is. Ubuntu will detect Windows and add it to GRUB automatically.

---

## 🔹 2. How to Prevent Ubuntu From “Stopping Working”

The issue you had (Ubuntu stopped working after 6 months) can happen if:

* Kernel or driver updates broke compatibility with your Snapdragon hardware.
* Ubuntu release was **short-lived** (25.04 support ends Jan 2026).
* Some experimental drivers weren’t stable.

### ✅ How to reduce problems

* Stick with **official kernels** (don’t add random PPAs unless needed).
* **Keep Windows bootloader intact** (so you can always boot Windows if Ubuntu fails).
* Use **LTS (24.04)** if you want max stability → but since your hardware is new, 25.04 might still be the better choice right now.
* Always keep a **live USB handy** → if Ubuntu breaks, you can boot from USB, chroot into the system, and repair GRUB or drivers.

---

## 🔹 3. Recommendation for You

* Use **25.04 ARM64** since Snapdragon X Elite is bleeding-edge hardware → you’ll likely get better support than with 24.04.
* Reuse your **old Ubuntu partition**, format it, and mount it as `/`.
* Let the installer also create a **small swapfile** automatically (no need for a swap partition anymore).

---

👉 When your ISO finishes downloading and you boot into the installer, do you want me to walk you through the **partitioning screen step by step** with exact clicks (so you don’t risk touching Windows)?
