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

![OPYTkJn](https://github.com/user-attachments/assets/8b3b976c-3da5-4f36-8472-dc6bebad1e55)

### 🔹 Mount the loopback image to a directory

![IPKY5BR](https://github.com/user-attachments/assets/25955fea-4a61-469c-9e28-81409ce81f47)

### 🔹 Verify the mount

![9PyqH01](https://github.com/user-attachments/assets/bdcc8254-52a4-4140-a323-0ad38e835380)

### 🔹 Unmount the filesystem

![Tba06Ic](https://github.com/user-attachments/assets/4aa18513-f151-48f4-9a58-fb0425a247a2)

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

![o5D7SA6](https://github.com/user-attachments/assets/48b57d7a-d88a-4429-867d-9627082d4662)

### 🔹 Simulate a removable device (loop again) and allow user access

![nNmip9s](https://github.com/user-attachments/assets/75a62604-a54e-4395-a97c-b45c5ea4ee6b)

###🔹 Test unmounting as a regular user (may require permissions adjustment)

![nNmip9s](https://github.com/user-attachments/assets/32d9c270-4c21-42e1-9d1d-40d86e4bc431)

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

