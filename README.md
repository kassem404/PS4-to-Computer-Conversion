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

## **Step 2: Set up PS4 Settings**
- Go to `PS4 Settings` -> `Sound & Screen`
- Turn off `System Music` and `Ket Tone`
- Go to `Video Resolution Output`
- Set `Screen Resolution` to `1080p`
- Set `RGB Range` to `Full`
- Set `HDR` to `Off`
- Set `Deep Colour Output` to `Off` (if available)
- Go to `PS4 Settings` -> `System` -> `System Information`
- Write down the Southbridge type on notes app or paper
- Southbridge used: Aeolia

---

## **Step 3: Set up Goldhen Settings**
- Go to `Goldhen` -> `Server Settings`
  - Enable FTP Server
  - Enable BinLoader Server

---

## **Step 4: Download PS4 Xplorer 2.0 & Payload Guest Apps**
- Sources:
  - Homebrew Store App on Jailbroken PS4 (if installed)
  - [Payload Guest App](https://pkg-zone.com/details/AZIF00003)
  - [PS4 Xplorer 2.0 App](https://pkg-zone.com/details/LAPY20009)
- If installing from a computer; copy the file to a USB then plug it in the PS4 and open `Goldhen` -> `Debug Settings` -> `Package Source` -> `Choose All` -> `Package Installer` -> `Install the Apps`

---

## **Step 5: Download Linux payloads**
- Download all payloads to try out or just one if you know your needs (512mb is enough for non-gaming workflows)
- Use at max the 1024mb Linux payload when booting Linux for the first time
- Sources:
  - This Repository [linux-512mb.bin](https://github.com/kassem404/PS4-to-Computer-Conversion/blob/main/linux-512mb.bin)
  - [GitHub](https://github.com/ArabPixel/ps4-linux-payloads/releases) ***Must use .elf files & rename to .bin***

---

## **Step 6: Download initramfs**
 - Sources:
   - [MediaFire](https://www.mediafire.com/file/wziaiuqttxlwwgp/initramfs.zip/file)
   - [GitHub](https://github.com/DionKill/ps4-linux-tutorial/blob/main/PS4%20Linux/initramfs.zip)

---

## **Step 7: Download kernel image**
- Kernel bzImage used: 5.15.15-obsidianx-1.0.0_release
- Sources:
  - This Repository [bzImage](https://github.com/kassem404/PS4-to-Computer-Conversion/blob/main/bzImage)
  - [GitHub](https://github.com/feeRnt/ps4-linux-12xx/releases/tag/v5.15.15__1.0.0)
  - [GitHub](https://github.com/rmuxnet/ps4-linux-12xx/releases)

---

## **Step 8: Download Linux distro**
- **Must rename file** to psxitarch.tar.xz / psxitarch.tar.gz depending on extension
- Distro publisher posts the username and password of the distro.
- Username used: qba
- Password used: loki
- Sources:
  - [MEGA](https://mega.nz/file/RyUVQARB#HZD49XXac_v2CYKD4Oqa7Tg1aiZ7ltH_cnDxixw9JjY)
  - [MegaUp](https://megaup.net/fadf9049f4e189a2f7961eeb2587b793/cachyos_final_fantasy_v2.tar.xz)

---

## **Step 9: Create directories**
- Open PS4 Xplorer 2.0
- You are by default inside the `root` directory / folder
- Enter `data` directory
- Create a new directory called `payloads` (if it does not exist)
- Go back to `root` directory
- Create a new directory called `linux` then enter it
- Create a new directory called `boot` inside `linux`
- Go back to `root` directory
- Enter `user` directory
- Enter `system` directory
- Create a new directory called `boot` inside `system`
- Close the App

---

## **Step 10: Copy files from USB drive**
- Plug in USB drive into the PS4
- Open PS4 Xplorer 2.0
- You are by default inside the `root` directory / folder
- Enter `mnt` directory then enter `usb0` directory where your files are stored
- Copy Linux payloads from USB, follow this path: `root` -> `data` -> `payloads`, paste
- Go back to `usb0` for copying
- Copy iniramfs, follow this path: `root` -> `data` -> `linux` -> `boot`, paste
- Go back to `usb0` for copying
- Copy kernel bzImage, follow this path: `root` -> `data` -> `linux` -> `boot`, paste
- Go back to `usb0` for copying
- Copy Linux distro, follow this path: `root` -> `user` -> `system` -> `boot`, paste
- Close the App
- Unplug USB drive

---

## **Step 11: Load the Linux Loader**
- Open Payload Guest App


## XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX


## **Step 5: Load the Linux Loader**
**Objective:** Boot the Linux loader from the PS4.

2. Select the Linux loader payload (e.g., `ps4-linux-loader.bin`).
3. Wait for the loader to initialize (screen may go black for a few minutes).
4. If the screen remains black, try pressing **CTRL+ALT+F1**, **CTRL+ALT+F2**, or **CTRL+ALT+F7** until the Linux console appears.
5. Touch grass during the installation process which might take an hour or a bit more (less time with internal SSD).

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
