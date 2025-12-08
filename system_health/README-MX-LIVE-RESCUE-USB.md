
# 🛠️ MX Linux Live Rescue USB — Reference Guide

This USB is a **dedicated emergency rescue & system repair disk** based on:

MX Linux 19.4 AHS (64-bit)  
Release: March 31, 2021  
USB Size: ~1.8 GB  
Free Space: ~128 MB (93% used)

This USB is **NOT a general storage device**. It is a **professional recovery tool**.

---

## ✅ What This USB Is For (Primary Uses)

This USB is designed to be used when:

- ✅ Your system fails to boot
- ✅ GRUB bootloader is broken
- ✅ You need to recover files from a dead PC
- ✅ You need to inspect or mount Linux/Windows disks
- ✅ You need to partition or format drives safely (GParted)
- ✅ You need to check disk health (SMART tools)
- ✅ You need to reset Linux user passwords
- ✅ You need to access encrypted disks for recovery
- ✅ You need to scan a Windows system offline

This is a **lifesaver USB** — not a storage stick.

---

## ✅ What This USB Is NOT For

❌ Do NOT use this USB for:
- Personal file storage
- Backups
- Media transfer
- Development work
- Encrypted vaults
- Daily usage

With only **128 MB free**, using it for storage can:
- Corrupt the filesystem
- Break the bootloader
- Destroy persistence

---

## ✅ What The Folders Mean

```

antiX/               → Core boot files
boot/                → Kernel & bootloader
EFI/                 → UEFI boot support
Live-usb-storage/    → Persistence layer (very limited space)
lost+found/          → Filesystem recovery folder
made-by-live-usb-maker → Creation marker
version              → MX Linux build info
cdrom.ico            → Windows icon file

````

⚠️ **Do NOT delete anything here.**

---

## ✅ How To Boot From This USB

1. Insert USB
2. Power on PC
3. Press:
   - `F12`, `Esc`, `F9`, or `Del` (varies by system)
4. Select USB device
5. Choose **MX Live Boot**

---

## ✅ Typical Rescue Workflows

### 🧰 1. Recover Files From a Dead System
- Boot from this USB
- Open file manager
- Mount internal disk
- Copy files to:
  - External hard drive
  - Another USB
  - Network location

---

### 🔧 2. Repair a Broken GRUB Bootloader
- Boot Live USB
- Open terminal
- Use MX Boot Repair tools
- Reinstall GRUB to system disk

---

### 💽 3. Partition or Format Drives
- Boot Live USB
- Open GParted
- Resize, create, or delete partitions safely

---

### 🔍 4. Check Disk Health
- Use SMART tools to detect failing drives
- Identify bad sectors early

---

## ✅ Free Space Status

Current status:
- Total Size: 1.8 GB
- Used: 1.7 GB
- Available: 128 MB

This means:
- ✅ Perfect as a rescue-only disk
- ❌ Not suitable as a storage USB

---

## ✅ Companion Devices (Recommended Setup)

This rescue USB is part of a **3-layer safety system**:

1. 🔐 Encrypted Secure USB → passwords & sensitive documents  
2. 🛠️ MX Live Rescue USB → emergency boot & recovery  
3. 💾 Large External Drive → backups & system snapshots  

This combination provides:
- Security
- Disaster recovery
- Long-term backup

---

## ✅ If You Ever Want To Repurpose This USB

⚠️ This will **destroy the rescue system**:

```bash
sudo wipefs -a /dev/sdX
sudo parted -s /dev/sdX mklabel gpt
sudo parted -s -a optimal /dev/sdX mkpart primary 0% 100%
sudo mkfs.exfat /dev/sdX1
````

Replace `sdX` with the correct USB device.

Only do this **after creating a new rescue USB**.

---

## ✅ Golden Rules

1. Never delete files from this USB.
2. Never format it casually.
3. Never store important data on it.
4. Always keep at least one rescue USB available.
5. Test boot it once every few months.

---

✅ STATUS: **VERIFIED WORKING MX LIVE RESCUE USB**

