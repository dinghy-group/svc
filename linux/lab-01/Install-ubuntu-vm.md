# Lab Guide – Installing Ubuntu 22.04 on VirtualBox

This document provides step-by-step instructions to create a local Linux lab using VirtualBox and Ubuntu 22.04.
You will install VirtualBox, download the Ubuntu ISO image, create a virtual machine (VM), install Ubuntu, and configure basic settings including terminal and SSH access.

---

## 1. Prerequisites

Before starting, make sure you have:

- A computer with at least 8 GB RAM (16 GB recommended)
- At least 40 GB free disk space
- Internet access
- BIOS/UEFI virtualization enabled:
  - Intel: VT-x
  - AMD: AMD-V

> If virtualization is disabled, VirtualBox may not show 64-bit options.

---

## 2. Install VirtualBox

Follow these steps:

1. Open a web browser.
2. Go to: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
3. Under "VirtualBox platform packages", choose your operating system:
   - Windows hosts
   - macOS hosts
   - Linux distributions
4. Download the installer.
5. Install VirtualBox:

**Windows:**
- Double-click the `.exe` file
- Click: Next → Next → Install → Finish

**macOS:**
- Open the `.dmg` file
- Run the `.pkg` installer
- Approve any security prompts

6. Accept default settings unless you want custom paths.
7. Open VirtualBox.

---

## 3. Download Ubuntu 22.04 ISO

1. Open a web browser.
2. Go to: [https://ubuntu.com/download](https://ubuntu.com/download)
3. Choose **Ubuntu 22.04 LTS**.
4. Click **Download**.
5. Save the `.iso` file (3–4 GB).
6. Wait for the download to complete.

---

## 4. Create a New Virtual Machine in VirtualBox

1. Open VirtualBox.
2. Click **New**.
3. Fill the first screen:
   - **Name:** Ubuntu-Lab
   - **Type:** Linux
   - **Version:** Ubuntu (64-bit)
4. Click **Next**.
5. Memory size:
   - Minimum: 4096 MB (4 GB)
   - Recommended: 6144 MB or 8192 MB
6. Click **Next**.
7. Hard disk:
   - Select "Create a virtual hard disk now"
   - Click **Create**
8. Hard disk file type:
   - Choose **VDI** (default)
   - Click **Next**
9. Storage type:
   - Choose "Dynamically allocated"
   - Click **Next**
10. Disk size:
    - Select 25 GB minimum (30–40 GB recommended)
    - Click **Create**

---

## 5. Attach the Ubuntu ISO to the VM

1. Select the VM (**Ubuntu-Lab**).
2. Click **Settings**.
3. Go to **Storage**.
4. Under Storage Devices, select the **Empty** disk icon.
5. On the right, click the small disk icon next to "Optical Drive".
6. Click **Choose a disk file…**
7. Select the downloaded `ubuntu-22.04.iso`.
8. Click **OK**.

---

## 6. Start the VM and Install Ubuntu 22.04

1. Select the VM → click **Start**.
2. The VM boots from the ISO.
3. Select **Install Ubuntu**.
4. Choose your language → **Continue**.
5. Choose keyboard layout → **Continue**.
6. On "Updates and other software":
   - Select **Normal installation**
   - Optional: Check "Download updates…"
   - Click **Continue**
7. On "Installation type":
   - Select **Erase disk and install Ubuntu**
   - This only affects the virtual disk
   - Click **Install Now** → confirm if asked
8. Choose your time zone → **Continue**.
9. Create your user:
   - **Name:** Student
   - **Computer name:** ubuntu-lab
   - **Username:** student
   - **Password:** student123 (example)
   - Recommended: Require password to log in
10. Click **Continue**.
11. Wait 5–15 minutes for installation to finish.
12. Click **Restart Now** when prompted.
13. If asked to remove installation medium, press **Enter**.
