![Design sem nome(5)](https://github.com/user-attachments/assets/8cdeef09-5df8-4893-a5ef-9ecdf3ba062c)

# 🧱 BORN2BEROOT – Linux Infrastructure & Security Project

**Born2beroot** is a Linux system hardening project that challenges students to configure a secure and fully operational virtual machine from scratch. Built under strict 42 guidelines, the project covers everything from EFI, LVM, and GRUB to SSH, sudo, and UFW — simulating real-world system administration with high security and performance standards.

This VM is not just a configuration task; it is a secure system environment built line-by-line, manually, to reflect your mastery over Linux internals, partitioning strategies, logical volumes, backup routines, and access controls.

🧠 It is a training ground for becoming a true system administrator.

---

## 🏅  Performance in the Project 

During the evaluation of Born2beroot, I delivered all mandatory setups, security reinforcements, and optimizations. Some of the key completed aspects:

   ✅ EFI, GRUB, and secure boot management  
   ✅ Proper partitioning using LVM (Volume Groups + Logical Volumes)  
   ✅ SSH service with root login disabled  
   ✅ User creation with restricted `sudo` access  
   ✅ UFW configured to whitelist only necessary services  
   ✅ Backup snapshot routines and `/etc` integrity control  
   ✅ Valgrind clean and system logs audit-ready

This reflects a strong understanding of system resilience, minimalism, and performance — all pillars for cybersecurity in production-grade systems.

---

## 📚 Key Features

🔹 System Setup – Linux Core Administration

- EFI System Partition (`/boot/efi`) and GRUB2 bootloader installation
- LVM setup: Physical Volumes → Volume Group → Logical Volumes
- Swap area defined and activated
- Partition structure using `ext4` for performance and journaling support

🔹 Security Hardening – Access & Firewall

- UFW firewall enabled with strict rules (`22`, `80`, and monitored ports)
- SSH configuration with `PermitRootLogin no`
- `sudo` configured for group `sudo` only, log policies in place
- Password complexity and account lockout policies

🔹 Automation & Logging

- Cron jobs for uptime logs and system checks
- Custom MOTD (Message of the Day)
- Snapshots via LVM or full system backups via `tar`

---

## 📁 Project Structure

    📦 born2beroot  
    ┗ 📜 signature.txt

---

## 📖 Concepts Overview

| Concept           | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| `/dev`           | Represents devices as files (e.g. disks, partitions)                        |
| `/dev/mapper`    | Holds mapped logical volumes (via LVM)                                      |
| `/dev/sda5`      | The 5th partition of your first storage device (`sda`)                      |
| EFI Partition    | Stores GRUB and bootloaders; must be FAT32 and mounted at `/boot/efi`      |
| LVM Group        | Volume Group containing Logical Volumes (e.g. `/dev/mapper/root`)           |
| Swap Partition   | Dedicated virtual memory area; activates with `swapon`                      |
| Filesystems      | `ext4`, `ext3`, `btrfs`, `XFS`, `JFS`, `FAT32` — each with pros and cons     |
| GRUB             | Bootloader that starts the OS via EFI or BIOS                               |
| `apt` / `sudo`   | Package manager / privilege elevation tool                                  |

---

## 🧠 Commands You’ll Use Often


    # See system date
    date

    # Save system state via full backup
    sudo tar czpvf born2beroot-backup.tar.gz --exclude=/proc --exclude=/sys --exclude=/dev --exclude=/run --exclude=/mnt /

    # Create LVM snapshot (if using LVM)
    sudo lvcreate --size 1G --snapshot --name snap_before_sudo /dev/mapper/ubuntu--vg-root

    # Show mounted disks
    lsblk

    # Show volume groups
    vgdisplay

# 🚧 Tutorials (Coming Soon)

I'm currently working on a detailed tutorial to help others navigate the LIBFT project more efficiently. This section will include:

    📹 Video Guide – A step-by-step walkthrough explaining key concepts and solutions.
    📄 PDF Guide – A structured document with explanations, tips, and best practices.

Stay tuned! The tutorial will be available soon. 🚀

# 🤝 Contributing

If you are also doing the Piscine, feel free to suggest improvements or share new approaches!

    📬 Contact: If you want to discuss solutions or exchange ideas, find me on Discord or GitHub!

<p align="center">
  <img src="https://github.com/user-attachments/assets/60cc3bc7-fb89-435b-af30-3da855287fce" alt="Imagem" />
</p>
