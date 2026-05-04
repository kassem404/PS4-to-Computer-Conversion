# PS4-to-Computer-Conversion
A simple guide for converting a PS4 into a Computer running Linux

- This guide covers all PS4 (Launch Edition / Fat) models: CUH-10xxA, CUH-11xxA, CUH-11xxB, CUH-12xxA, and CUH-12xxB
- Model used: CUH-1116A (Found on the bottom of the PS4)
- This guide uses the **internal drive method**, which installs Linux into the PS4's main drive. The PS4's operating system will not be deleted and the system will be set up to dual-boot Linux.
- **Requires** a Computer, USB drive in exFAT format, keyboard and mouse (wired or wireless)

---

## **Step 1: Jailbreak the PS4 (Any method)**
- Payload used: Goldhen v2.4b18.7 (Avoid v2.4b18.8)
- Sources:
  - This Repository [payload.bin](https://github.com/kassem404/PS4-to-Computer-Conversion/blob/main/payload.bin)
  - [Ko-fi](https://ko-fi.com/s/5d29f9e29c) ***Must rename goldhen.bin to payload.bin***

---

## **Step 2: Note down Software & Southbridge versions**
- Found in PS4 Settings -> System -> System Information
- Software version used: 11.52
- Southbridge used: Aeolia

---

## **Step 3: Enable Goldhen Server Settings**
- Found in Goldhen Settings -> Server Settings
  - Enable FTP Server
  - Enable BinLoader Server

---

## **Step 4: Download PS4 Xplorer 2.0 & Payload Guest Apps**
- Sources:
  - Homebrew Store App on Jailbroken PS4 (if installed)
  - [Payload Guest App](https://pkg-zone.com/details/AZIF00003)
  - [PS4 Xplorer 2.0 App](https://pkg-zone.com/details/LAPY20009)
- If installing from a computer; copy the file to a USB then plug it in the PS4 and open Goldhen -> Debug Settings -> Package Source -> Choose All -> Package Installer -> Install the Apps

---

## **Step 5: Download Linux Payloads**
- Download all payloads to try out or just one if you know your needs (512mb is enough for non-gaming workflows)
- Use at max the 1024mb Linux payload when booting Linux for the first time
- Sources:
  - This Repository [linux-512mb.bin](https://github.com/kassem404/PS4-to-Computer-Conversion/blob/main/linux-512mb.bin)
  - [GitHub](https://github.com/ArabPixel/ps4-linux-payloads/releases) ***Must use .elf files & rename to .bin***

---

## **Step 6: Open PS4 Xplorer 2.0 App**
- Enter `mnt` directory
- Find your `usb` files
- Select and copy the Linux payloads
- Go back
- Enter `data` directory
- Create a folder named `payloads` if it does not exist
- Paste the Linux payloads into `payloads` folder

---

### **Step 7: Download kernel image**
- Kernel bzImage used: 5.15.15-obsidianx-1.0.0_release
- Source:
  - [GitHub](https://github.com/feeRnt/ps4-linux-12xx/releases/tag/v5.15.15__1.0.0)

- Installation may take **1 hour or more** (less time with an internal SSD).
- If nothing is displayed, try pressing **CTRL+ALT+F1**, **CTRL+ALT+F2**, or **CTRL+ALT+F7** repeatedly.


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

## Additional Resources:
- Link: https://dionkill.github.io/ps4-linux-tutorial/postinstall.html
