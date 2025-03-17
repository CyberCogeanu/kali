```md
 - SHA256sum: 1b1a99e2d66c1392856181abc18bd94a0563bab705b6fbd0baca463c9d3faa66
 - https://cdimage.kali.org/kali-2024.4/kali-linux-2024.4-vmware-amd64.7z
 - kali-linux-2024.4-vmware-amd64.7z
```
```md
- Open a virtual machine: kali-linux-2024.4-vmware-amd64.vmdk
- Edit Virtual machine settings
  - Memory: from 2GB to 16GB (16 384 MB)
  - number of processors from 2 to 1 | Number of cores from 2 to 8

```
After login in termina change password for the default user kali

```bash
passwd kali
```
```md
# Updating Kali Linux (VMware) to the Latest Version

This guide will walk you through updating your Kali Linux pre-prepared VMware image to the latest possible version and installing all available packages.

## 1. Verify Your Internet Connection
Before starting, ensure your VM has internet access by running:

```bash
ping -c 4 google.com
```

If there's no connection, check your network settings in VMware.

---

## 2. Update the Package Lists and System
First, refresh the package lists and upgrade all installed packages:

```bash
sudo apt update && sudo apt full-upgrade -y
```

This will download and install the latest updates.

---

## 3. Remove Unnecessary Packages
Clean up unnecessary packages to free space:

```bash
sudo apt autoremove -y && sudo apt autoclean
```

---

## 4. Install the Kali Everything Package
To install all available Kali tools:

```bash
sudo apt install -y kali-linux-everything
```

This will take time, depending on your internet speed.

---

## 5. Upgrade the Kernel (Optional but Recommended)
For the latest kernel and security updates:

```bash
sudo apt install -y linux-image-amd64
sudo reboot
```

---

## 6. Verify the Update
After rebooting, confirm that Kali is fully updated:

```bash
lsb_release -a
uname -r
```

This should show the latest Kali Linux version and kernel.

---

## 7. Install VMware Tools (Optional but Recommended)
To enable features like copy-paste, shared folders, and better display support:

```bash
sudo apt install -y open-vm-tools-desktop
sudo reboot
```

---

## 8. Final Cleanup
To ensure no broken dependencies:

```bash
sudo dpkg --configure -a
sudo apt --fix-broken install
```

Your Kali Linux VM is now fully updated with all available tools installed!
```
