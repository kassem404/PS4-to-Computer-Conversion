# PS4-to-Computer-Conversion
A simple guide for converting a PS4 into a Computer running Linux.

- This guide covers all PS4 Launch Edition (PS4 "Fat") models: CUH-10xxA, CUH-11xxA, CUH-11xxB, CUH-12xxA, and CUH-12xxB.
- Model used: CUH-1116A (Found on the bottom of the PS4)
- This guide uses the **internal drive method**, which installs Linux into the PS4's main drive. The PS4's operating system will not be deleted and the system will be set up to dual-boot Linux.
- **Requires** a keyboard and mouse (wired or wireless).

---

## **Step 1: Jailbreak the PS4**
- Use any jailbreak method compatible with your PS4 firmware.
- **Payload:** **Goldhen v2.4b18.7** or lower (Newer versions may cause issues with Linux)
- **Sources:**
  - This Repository (payload.bin)
  - [GoldHEN GitHub](https://github.com/GoldHEN/GoldHEN/releases/tag/2.4b17.3)
  - [Ko-fi (GoldHEN)](https://ko-fi.com/s/5d29f9e29c)

---






## **Step 2: Download Payload Guest App**
**Objective:** Install an app to load custom payloads.

- **Sources:**
  - [PKG Zone (AZIF00003)](https://pkg-zone.com/details/AZIF00003)
  - Homebrew Store (on Jailbroken PS4)
  - This Repository

---

## **Step 3: Transfer Linux Files to PS4**
**Objective:** Move Linux image and loader to your PS4.

### **Option 1: Using FileZilla (Recommended)**
1. Download and install [FileZilla](https://filezilla-project.org/download.php) on your PC.
2. Connect to your PS4 using the IP address displayed by the Payload Guest App (usually `192.168.x.x:21`).
   - Username: `anonymous`
   - Password: (leave blank or use `anonymous`)
3. Navigate to `/user/` on the PS4.
4. Upload the Linux image and loader files to this directory.

### **Option 2: Using USB/HDD/SSD (Alternative)**
1. Format a USB drive as **exFAT** or **FAT32**.
2. Copy the Linux image and loader files to the root of the USB.
3. Insert the USB into the PS4.
4. Use [PS4 Xplorer](https://pkg-zone.com/details/LAPY20009) to copy the files to `/user/`.

---
**Note:**
- Installation may take **1 hour or more** (less time with an internal SSD).
- If nothing is displayed, try pressing **CTRL+ALT+F1**, **CTRL+ALT+F2**, or **CTRL+ALT+F7** repeatedly.

---
---

## **Step 4: Prepare the Linux Image**
**Objective:** Download a compatible Linux distribution for PS4.

- **Recommended Distros:**
  - Ubuntu 20.04 LTS
  - Debian 11
  - Fedora
- **Sources:**
  - [PS4 Linux Loader GitHub](https://github.com/fail0verflow/ps4-linux)
  - [PSXHax Forum](https://www.psxhax.com/threads/ps4-linux-loader.5802/)
- **Important:** Use **PS4-specific images** (`.img.gz` or `.iso`). Generic x86_64 ISOs will **not** work.

---

## **Step 5: Load the Linux Loader**
**Objective:** Boot the Linux loader from the PS4.

1. Open the **Payload Guest App** on your PS4.
2. Select the Linux loader payload (e.g., `ps4-linux-loader.bin`).
3. Wait for the loader to initialize (screen may go black for a few minutes).
4. If the screen remains black, try pressing **CTRL+ALT+F1**, **CTRL+ALT+F2**, or **CTRL+ALT+F7** until the Linux console appears.

---
---

## **Step 6: Install Linux to Internal Disk**
**Objective:** Install Linux on the PS4’s internal storage.

1. Follow the on-screen prompts to start the installation.
2. Select the internal disk (usually `/dev/sda` or `/dev/sdb`).
   **⚠️ Warning:** This will **erase all data** on the selected disk.
3. Proceed with the installation (may take **1-2 hours**).
4. Set up a user account and password when prompted.

---
---

## **Step 7: First Boot and Configuration**
**Objective:** Boot into Linux and perform initial setup.

1. After installation, select **Reboot** from the Linux loader menu.
2. Use the **Payload Guest App** to load the Linux loader again.
3. Log in with your credentials.
4. Update the system:
   ```bash
   sudo apt update && sudo apt upgrade -y

---
## Troubleshooting
   **Issue**                     | **Solution**                                      |
 |-------------------------------|---------------------------------------------------|
 | Black screen after loading    | Try different TTYs (CTRL+ALT+F1-F7)               |
 | Installation freezes          | Wait 1-2 hours; check disk space                  |
 | No HDMI signal                | Do **not** unplug HDMI; restart PS4               |
 | LED strip not dark blue       | Force shutdown and retry                          |
