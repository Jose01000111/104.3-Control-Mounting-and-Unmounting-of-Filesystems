# 📁104.3: Control Mounting and Unmounting of Filesystems

## 📝 Introduction
In this lab, I practiced manually mounting and unmounting filesystems, configuring persistent mounts, and managing removable devices. I also explored how to identify partitions using labels and UUIDs, and gained basic awareness of systemd mount units.


I’ve included some helpful links to guide you through the lab and for studying afterward:

[EXAM OBJECTIVE 104.3](https://www.lpi.org/our-certifications/exam-101-102-objectives/#104.3_Control_mounting_and_unmounting_of_filesystems)

[OBJ.104.3 NOTES]()

[OBJ.104.3 LAB](https://1drv.ms/w/c/354f1c8d534fbced/EYSMSGN-WCJNhGUUcUGPqaQBDhp9DecYouOP4zA46M_WeQ?e=cGYP33)

---

## 1️⃣ Manually Mount and Unmount Filesystems
### 🔹 Create and format a loopback image file

bash
Copy
Edit
dd if=/dev/zero of=/tmp/labdisk.img bs=1M count=100
mkfs.ext4 /tmp/labdisk.img
### 🔹 Mount the loopback image to a directory

bash
Copy
Edit
mkdir /mnt/labmount
mount -o loop /tmp/labdisk.img /mnt/labmount
### 🔹 Verify the mount

bash
Copy
Edit
mount | grep labmount
df -h /mnt/labmount
### 🔹 Unmount the filesystem

bash
Copy
Edit
umount /mnt/labmount
## 2️⃣ Configure Filesystem Mounting on Bootup
### 🔹 Create a new mount point and entry in /etc/fstab

bash
Copy
Edit
mkdir /mnt/persistent
cp /tmp/labdisk.img /labdisk.img
echo "/labdisk.img /mnt/persistent ext4 loop 0 0" >> /etc/fstab
### 🔹 Mount using fstab entry

bash
Copy
Edit
mount -a
df -h | grep persistent
## 3️⃣ Configure User-Mountable Removable Filesystems
### 🔹 Create a new mount point under /media/

bash
Copy
Edit
mkdir /media/myusb
### 🔹 Simulate a removable device (loop again) and allow user access

bash
Copy
Edit
mount -o loop,uid=$(id -u),gid=$(id -g) /labdisk.img /media/myusb
🔹 Test unmounting as a regular user (may require permissions adjustment)

bash
Copy
Edit
umount /media/myusb
## 4️⃣ Use of Labels and UUIDs for Identifying and Mounting Filesystems
### 🔹 View UUIDs and labels of partitions

bash
Copy
Edit
blkid
lsblk -f
### 🔹 Add a label to a filesystem

bash
Copy
Edit
e2label /labdisk.img LABDISK
### 🔹 Use the label in /etc/fstab

bash
Copy
Edit
echo "LABEL=LABDISK /mnt/bylabel ext4 loop 0 0" >> /etc/fstab
mkdir /mnt/bylabel
mount -a
## 5️⃣ Awareness of systemd Mount Units
### 🔹 Review an auto-generated .mount unit (read-only awareness)

bash
Copy
Edit
systemctl list-units --type=mount
### 🔹 Optional: Create a custom .mount unit (advanced users only)
Explore /etc/systemd/system and create a .mount file for persistent mounting.


## 🧠 What I Learned
In this lab, I learned how to manually mount and unmount filesystems and make them persist across reboots using /etc/fstab. I practiced working with UUIDs and labels to make mounting more reliable, especially when device names change. I also explored how removable devices can be configured for user mounting and gained awareness of how systemd manages mount points automatically. 🧩📚

