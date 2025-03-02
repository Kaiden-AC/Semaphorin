<div align="center">
  <img src="https://files.catbox.moe/x7b0e2.png" height="128" width="128" style="border-radius:25%">
  <h1>Semaphorin</h1>
  <p><strong>64-Bit iOS Downgrade, Dualboot, and Jailbreak Utility</strong></p>
</div>

<p align="center">
  <strong>Supported iOS Versions:</strong> iOS 7.0.6 - 12.1 <br>
  <strong>Supported Devices:</strong> A7 - A11
</p>


## Discontinued

This fork has been discontinued and archived, I will be working on a more functional and easy-to-use downgrade tool in the future.

## Compatibility Matrix

This table outlines the functionality expected on each supported iOS version after downgrading with Semaphorin.

| iOS        | App Store | Cydia   | Tweaks | Respring | Cellular | Sideloadly | iTunes |
|------------|-----------|---------|--------|----------|----------|------------|--------|
| 7.0.6      | ✅        | ✅      | ✅     | ✅       | ✅       | ✅         | ✅     |
| 7.1.2      | ✅        | ✅      | ✅     | ✅       | ✅       | ✅         | ✅     |
| 8.4.1      | ✅        | ✅      | ✅     | ✅       | ❌       | ✅         | ✅     |
| 9.3        | ✅        | ✅      | ✅     | ✅       | ✅       | ❌         | ❌     |
| 10.3.3     | ✅        | ✅      | ✅     | ✅       | ✅       | ❌         | ❌     |
| 11.3       | ✅        | ✅      | ✅     | ✅       | ✅       | ❌         | ❌     |
| 12.1       | ✅        | ✅      | ✅     | ✅       | ✅       | ❌         | ❌     |

**Legend:**

*   ✅ = Functionality is fully operational.
*   ❌ = Functionality is not working or not fully supported.

## Important Warning

**Data Loss:** This script will **erase all data** on your device, including the existing operating system (unless downgrading to iOS 10.3.3 or later). **Back up your device completely before proceeding.** Data lost during this process cannot be recovered.

**Risk:** Use this script at your own risk. I am not responsible for any damage or loss of data resulting from its use.

## Getting Started

### Prerequisites

*   **macOS:** Catalina (10.15) or later.
*   **Python:** 3.6 or later.
*   **Hardware:** An Intel-based Mac (AMD CPUs/Hackintoshes are not supported).
*   **Internet:**  A stable internet connection.
*   **Storage:** At least 20 GB of free disk space.
*   **USB:** A USB Type-A port and a Lightning cable (USB Type-C ports and dongles can be unreliable)
*   **Working iDevice:** The device must be functional enough to allow the script to back up critical files, including `apticket.der`, `sep-firmware.img4`, `Baseband`, and `keybags`.

### Installation

1.  **Install Git (if needed):** Open Terminal and run `xcode-select install`.
2.  **Clone the Repository:** In Terminal, run:
    ```bash
    git clone https://github.com/Kaiden-AC/Semaphorin.git && cd Semaphorin
    ```

### Usage

1.  **Enter DFU Mode:** Connect your device to your Mac and put it into DFU (Device Firmware Update) mode. (See online tutorials for specific device instructions if needed).

2. **Initial Restore:** Run the downgrade script using the following command in Terminal:
    ```bash
    sudo ./semaphorin.sh <target_ios_version> --restore
    ```
    Replace `<target_ios_version>` with the iOS version you wish to downgrade to (e.g., `sudo ./semaphorin.sh 9.3 --restore`).

3.  **Current iOS Version Input:** The script will prompt you for your **current** iOS version. Type in the correct version and press Enter to continue.

4.  **Follow On-Screen Instructions:** The script will guide you through the downgrade process, including rebooting multiple times. This process may take a considerable amount of time.

5. **Post-downgrade Jailbreak:**
    *   **iOS 9 or later:** Look for the jailbreak application on your home screen.
    *   **iOS 8 or below:** Device will already be jailbroken.

### Subsequent Boots

After the initial downgrade, you can boot into the downgraded iOS version using:

```bash
sudo ./semaphorin.sh <downgraded_ios_version> --boot
```
    
  Replace `<downgraded_ios_version>` with the version you have already downgraded to (e.g., `sudo ./semaphorin.sh 9.3 --boot`).

## Troubleshooting

### Deep Sleep Issues
Your device may experience "deep sleep" issues after downgrading, causing it to not wake up when locking it. 
* **Workaround:** Install the tweak "Fiona" from Julioverne's repo. This tweak may have a small effect on your battery life.
 * Repo URL: `julioverne.github.io`

### WiFi Issues

Issues connecting to Wi-Fi networks (e.g., incorrect password errors) can occur after downgrading. Use an **open Wi-Fi** network to bypass this problem. You can create a temporary open network from your macOS machine using Internet Sharing or on Linux using `linux-wifi-hotspot`. Take care to secure your network if you use this method.

### Safari not working (iOS 10)
Use the **FileManager** app on the home screen as a temporary replacement. It has a built-in download manager.

### Safari and other apps broken (iOS 7)
1. Reboot your device.
2. Open the Terminal app.
3. Enter `su -` and press Enter.
4. Enter `alpine` as the password and hit Enter.
5. Enter `reload` and hit Enter. This will patch sandbox and load all your tweaks. You may have to do this twice to respring your device.

## Credits

This project would not be possible without the incredible work of these individuals:

*   y08wilm: Original Semaphorin code
*   [PsychoTea](https://github.com/PsychoTea/):  MeridianJB
*   [coolstar](https://github.com/coolstar): Electra and Chimera jailbreaks.
*   [edwin170](https://github.com/edwin170): Contributions to resolving cellular, iCloud, audio and other issues.
*   johndoe123: A7 iOS 7 downgrade guide.
*   [LukeZGD](https://github.com/LukeZGD/): Updated cydia.tar and icon fixes for iPads
*   [TheRealClarity](https://github.com/TheRealClarity): wtfis.app, for sandbox patch on iOS 7.
*   [Nathan](https://github.com/verygenericname): SSH ramdisk and iBoot64Patcher fork.
*   [Mineek](https://github.com/mineek): seprmvr64 and other patches.
*   [Luna](https://github.com/lunaynx): DFU script.
*   [tihmstar](https://github.com/tihmstar): pzb, iBoot64Patcher, liboffsetfinder64, img4tool.
*   [sarah](https://github.com/plooshi): Patches and bug fixes
*   [xerub](https://github.com/xerub): img4lib and restored_external.
*   [Cryptic](https://github.com/Cryptiiiic): iBoot64Patcher and liboffsetfinder64 forks.
*   [libimobiledevice](https://github.com/libimobiledevice): Various tools used in the project.
*   [nikias](https://github.com/nikias): Keeping libimobiledevice up to date.
*   [Nick Chan](https://github.com/asdfugil): General help with patches and iBoot.
*   [Serena](https://mastodon.social/@CoreSerena): Boot ramdisk assistance.
*   [planetbeing](https://github.com/planetbeing): dmg tool from xpwn.
*   [exploit3dguy](https://github.com/exploit3dguy): iPatcher for iBoot patching on iOS 7.
*   [dora2-ios](https://github.com/dora2-iOS): iPwnder
*   [NyanSatan](https://github.com/NyanSatan): fixkeybag
