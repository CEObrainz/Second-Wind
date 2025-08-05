# Second Wind: Nintendo Switch Installation Guide

## Prerequisites

- A Nintendo Switch (moddable or modchipped)
- A physical or digital copy of *The Legend of Zelda: Breath of the Wild* v1.6.0 with its DLCs
- A 64-bit PC running Windows (recommended) or Linux
- A microSD card with at least 20 GB of free space

---

## Modding Your Console

To use mods or play via emulator, your console **must be modded**. Modding unlocks access to custom themes, homebrew, and mod support without restricting normal functionality.

> ⚠️ Not all Switch models are soft-moddable, but all can be modded with a modchip.

Refer to [this guide](https://switch.hacks.guide/) to determine how to mod your specific Switch model.

If your Switch is already modded, skip ahead to the next section.

---

## Dumping the Game

To install Second Wind (even on-console), you must dump your copy of *Breath of the Wild* to your PC. The full dump is approximately 15 GB, so ensure both your SD card and PC have at least 20 GB of free space.

Check that you are running **version 1.6.0** with **DLC version 3.0**. Nintendo's more recent updates (1.8.0+) are incompatible with mods.

<img width="3838" height="2158" alt="465664237-3ca2a0e2-4db2-458a-a6fc-b7e12c29ba2f" src="https://github.com/user-attachments/assets/8f433f9b-8f1b-4cdc-9806-6d85fa20942c" />

### Dumping Options
There are two methods available, both covered on [this guide](https://dardel.codeberg.page/nxdumpguide/):

- **Dumping RomFS (Modders)** — Recommended for console users
- **Dumping to PC (Emulator Users)** — Use this if playing on an emulator, then extract the RomFS

After dumping the game and DLCs in RomFS format, store them in a well-organized location such as:
- `C:/Games/Switch/Breath of the Wild/Game+Update/romfs`
- `C:/Games/Switch/Breath of the Wild/DLC/romfs`

You may delete the files from your SD card once transferred.

---

## Optional – Installing Ryubing (Emulator)

**Ryubing** is a community continuation of the discontinued **Ryujinx** emulator. Follow the setup instructions on [this page](https://git.ryujinx.app/ryubing/ryujinx/-/wikis/Setup-&-Configuration-Guide).

> 🔧 For enhanced resolution and framerate, try [NX-Optimizer](https://www.nxoptimizer.com/games/breath-of-the-wild/).

### Extracting RomFS in Ryubing

1. Ensure BotW version 1.6.0 + DLC 3.0 is installed and shows properly at the bottom right of the title screen.
   
2. **Dump Game + Update**:
   - Right-click BotW → `Extract Data > RomFS`
   - Choose: `C:/Games/Switch/Breath of the Wild/Game+Update/romfs`

<img width="1080" height="653" alt="465781022-df150629-d036-4aef-9fef-8234731bd9a4-1" src="https://github.com/user-attachments/assets/f9e6afd4-f779-46d7-9140-618485f17e72" />

3. **Dump DLC**:
   - Right-click BotW → `Extract Data > DLC RomFS`
   - Select `01007EF00011F001`
   - Dump to: `C:/Games/Switch/Breath of the Wild/DLC/romfs`

<img width="1205" height="644" alt="465781035-bede96f8-90af-4bb7-afc7-f525ef059ccb" src="https://github.com/user-attachments/assets/70ccf56b-70a8-450c-ab8a-1caa31f5f0c3" />
<img width="382" height="327" alt="465781098-23de6f28-42e6-4cf9-9a3f-8dab7be8789a" src="https://github.com/user-attachments/assets/57edc69c-b87e-47f9-8f47-109f11626755" />

---

## Setting Up BCML

> ❗ UKMM does not currently support Switch builds. This guide uses **BCML** instead.

### Step 1: Install Prerequisites

1. Download and install:
   - [Visual C++ Redistributable](https://aka.ms/vs/17/release/vc_redist.x64.exe)
   - [Python 3.8.10 for Windows](https://www.python.org/ftp/python/3.8.10/python-3.8.10-amd64.exe)
     - Tick **"Add Python 3.8 to PATH"** before installing.

<img width="826" height="504" alt="465776633-824256eb-b7c8-4b77-95c3-d030883395c4" src="https://github.com/user-attachments/assets/d448518e-e35a-4b4c-8322-38489d15b9e2" />

Linux users: Refer to your distro's package manager/documentation.

2. Open Command Prompt (Win+R → `cmd`) and run:
   ```bash
   pip install bcml==3.10.4
   ```

> Note: BCML 3.10.4 is preferred for compatibility with older mods. Newer versions will cause a Definition error with BNP v2 mods.  
> If you get a Syntax error when running this command, make sure that you are NOT in the Python console.

3. Once installed, run:
   ```bash
   bcml
   ```

### Step 2: Configure BCML

1. Go to **Settings** tab
2. Check the box **"Use Switch Mode"** (bottom-right)

<img width="2881" height="1533" alt="465779484-f1001f4d-16cb-4538-8758-0bb28081f628-1" src="https://github.com/user-attachments/assets/3507e1b4-8ed3-4709-9cc5-72d1a6aa4275" />

#### Game Folders

- **Base+Update Directory**: `C:/Games/Switch/Breath of the Wild/Game+Update/romfs`
- **DLC Directory**: `C:/Games/Switch/Breath of the Wild/DLC/romfs`

> ✅ A green border confirms the path is valid.

#### Options

- **Game Language**: Select based on your game region and language following the `XXyy` format, where `XX` is your region (`EU`, `US`, `JP`) and `yy` your game language (`en`, `fr`, etc.)
- **Merged Export Directory**:
  - On-console: `C:/ModPack`
  - Ryubing: `C:/Users/YourUsername/AppData/Roaming/Ryujinx/sdcard/atmosphere/contents`

> Optional: Enable "Disable links for master mod" if you do not want to export directly to `C:/`

<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/1b1e7bf8-daff-4dc6-9f13-a67cbdeaeff9" />

> Here's an example of a properly configured BCML.
 
Click **Save** once done.

---

## Installing Second Wind

1. Download the latest `.bnp` release from [Second Wind Switch GitHub](https://github.com/Nitr4m12/Second-Wind-Switch/releases/latest)
2. Do **not** extract the `.bnp` file
3. Install using one of the following:
   - Double-click the `.bnp`
   - Drag it into the BCML window
   - Use the `+` button in the **Mods** tab

### Mod Load Order

- Set **Second Wind** to **priority 100** (lowest)
- Click `Show Sort Handles` (or press `Ctrl+S`) to reorder

---

## Launching the Game with Mods

### Emulator (Ryubing)

1. Launch Ryubing
2. Right-click BotW → **Manage Mods**
3. Ensure mod `01007EF00011E000` is listed and enabled

> The DLC mod `01007EF00011F001` may not appear in the mod list. As long as it exists alongside the main mod folder in the correct directory, it will load.

### Console

1. Navigate to your `Merged Export Directory` (e.g. `C:/ModPack`)
2. You should see:
   - `01007EF00011E000`
   - `01007EF00011F001`

3. Copy both folders to your SD card under:
   ```text
   SD:/atmosphere/contents/
   ```

> Hold `L` while launching BotW to temporarily disable mods. Delete both folders to fully uninstall.

<details>
<summary>Final Mod Layout on microSD</summary>

```text
 💾 SD:/
 ├─ 📂 atmosphere/
 │  ├─ 📂 contents/
 │  │  ├─ 📂 01007EF00011E000/
 │  │  │  ├─ 📂 romfs/
 │  │  │  │  ├─ 📜 ...
 │  │  ├─ 📂 01007EF00011F001/
 │  │  │  ├─ 📂 romfs/
 │  │  │  │  ├─ 📜 ...
```
</details>

---

## Confirming Installation

- Check the title screen for the **Second Wind** logo
- If enabled, all shrines will have brand-new layouts under the **Shrine Overhaul**

🎉 You're now ready to enjoy Second Wind on your Nintendo Switch!
