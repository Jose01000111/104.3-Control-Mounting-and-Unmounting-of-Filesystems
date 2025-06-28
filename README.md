# 📁104.3: Control Mounting and Unmounting of Filesystems

## 📝 Introduction
In this lab, I practiced manually mounting and unmounting filesystems, configuring persistent mounts, and managing removable devices. I also explored how to identify partitions using labels and UUIDs, and gained basic awareness of systemd mount units.


I’ve included some helpful links to guide you through the lab and for studying afterward:

[EXAM OBJECTIVE 104.3](https://www.lpi.org/our-certifications/exam-101-102-objectives/#104.3_Control_mounting_and_unmounting_of_filesystems)

[OBJ.104.3 NOTES](https://1drv.ms/w/c/354f1c8d534fbced/EcwIi7isjxNGkyRGKsCigR8B0_hn2e2xOtcvoj-4W12OQg?e=2R85f1)

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

![o5D7SA6](https://github.com/user-attachments/assets/1c1a7c32-4fe2-4fb4-92c5-0896ff98f1e0)

### 🔹 Mount using fstab entry

![GSodaJB](https://github.com/user-attachments/assets/6349bcce-1220-40b3-a45c-9535ac360bc0)

## 3️⃣ Configure User-Mountable Removable Filesystems
### 🔹 Create a new mount point under /media/

![nNmip9s](https://github.com/user-attachments/assets/06678906-266d-44b1-8cfa-b141751f92a1)

### 🔹 Simulate a removable device (loop again) and allow user access

![8F8HAeO](https://github.com/user-attachments/assets/0832899f-e831-47d2-9291-4cab1a88b658)

###🔹 Test unmounting as a regular user (may require permissions adjustment)
![S7TjEtp](https://github.com/user-attachments/assets/3c505c30-172e-4417-887c-fd8020575f58)



## 4️⃣ Use of Labels and UUIDs for Identifying and Mounting Filesystems
### 🔹 View UUIDs and labels of partitions

![RN5q1JL](https://github.com/user-attachments/assets/8c5c3232-5635-4ebd-b42b-b4467845d954)

![8s0trYz](https://github.com/user-attachments/assets/37824ab1-13f9-4990-85b6-3943174ad856)

### 🔹 Add a label to a filesystem

![6w5ZGiK](https://github.com/user-attachments/assets/b071f8b2-dfa1-46f8-8006-ca1a8b1192b7)

### 🔹 Use the label in /etc/fstab

![VktQ86Y](https://github.com/user-attachments/assets/1df89f1f-720a-4093-b798-e17508158850)

## 5️⃣ Awareness of systemd Mount Units
### 🔹 Review an auto-generated .mount unit (read-only awareness)

![a7oKfdG](https://github.com/user-attachments/assets/7e873fa3-2248-404e-8af4-619e318af812)

## 🧠 What I Learned
In this lab, I learned how to manually mount and unmount filesystems and make them persist across reboots using /etc/fstab. I practiced working with UUIDs and labels to make mounting more reliable, especially when device names change. I also explored how removable devices can be configured for user mounting and gained awareness of how systemd manages mount points automatically. 🧩📚

