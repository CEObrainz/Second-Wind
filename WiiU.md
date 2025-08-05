# Second Wind: Wii U Installation Guide

## Prerequisites

- A Wii U console  
- A physical or digital copy of *The Legend of Zelda: Breath of the Wild* version 1.5.0 with its DLCs (required for most mods including Second Wind)  
- A computer running Windows, Linux, or macOS capable of reading/writing to an SD card, with at least 20 GB of free space  
- An SD card with at least 20 GB of free space  

---

## Optional – Modding Your Console

To play mods on actual hardware, you’ll need a modded Wii U. Modding your console does not restrict its functionality. In fact, it enables additional features such as mods and access to community-hosted online services like Pretendo. If you're planning to play via emulator, you can dump your game without a modded console.

If your console is already modded with **Tiramisu**, you may proceed directly to the next section.

While **Aroma** is a newer option, its implementation of **Sdcafiine**, the plugin required for loading mods, currently suffers from performance issues and instability. Therefore, we recommend using **Tiramisu** for now.

To mod your console, we suggest following [this guide](https://web.archive.org/web/20240101140009/https://wiiu.hacks.guide/#/). For visual learners, you can supplement it with a video tutorial, but avoid following YouTube videos blindly. Always prefer the linked guide and **make a NAND backup** before proceeding.

---

## Dumping the Game

To install Second Wind (and to run it on an emulator), you must dump your copy of *Breath of the Wild* and transfer it to your PC, even if you intend to play on the console. The full dump is approximately 15 GB, so ensure you have at least 20 GB of free space on both your SD card and PC.

If you’ve already dumped your game using the **Dumpling** method, and you’re familiar with its file structure, you can skip to the next section.

### Step-by-Step:

1. **Disable auto power-off** and similar power-saving features in the console's settings.
2. Insert the game disc (if needed) and ensure the game is fully updated with all DLCs.  
   - The title screen should display `ver. 1.5.0` and `DLC ver. 3.0`.

<img width="960" height="540" alt="457677277-a319fe53-0183-4f47-a918-45e3eeeacaf9" src="https://github.com/user-attachments/assets/454436c0-e86d-4e27-8508-99bca25afc5a" />

3. On your Wii U, open the Internet Browser and visit:  
   **https://dumplingapp.com/**  
   Bookmark this URL for convenience.

4. Click **Launch Dumpling**. If it doesn’t load within a minute, hold the power button to turn off your console and try again.

5. In Dumpling, choose **Dump a game disc** or **Dump digital games**, depending on your version of BotW.

<img width="1920" height="1080" alt="457677734-7dcf906d-cb6f-4c37-98bd-47648dbc2035" src="https://github.com/user-attachments/assets/d63cc5a5-7c05-49d8-a414-d04638fd2f84" />

6. When prompted, confirm **Yes** to dump the update and DLC files.

<img width="1920" height="1080" alt="457677942-86701335-3334-42c1-b4a3-bc3f0515b916" src="https://github.com/user-attachments/assets/d5044ac4-f60c-4212-bbfc-a273ff471b6e" />

7. Review the settings. In most cases, the default options are ideal:
   - Confirm the **Dump Destination** is your SD card.
   - Allow the **initial scan for required empty space**.
   - Enable **Merge Saves to Default Cemu User** if available.

8. Press `[Confirm]` and wait for the dump to complete (approx. 1–2 hours).

<img width="1920" height="1080" alt="457677955-920aa4f2-a985-4a51-885d-942cff0a9e3a" src="https://github.com/user-attachments/assets/097b2490-2e8d-4853-823a-c658a22f24c6" />
<img width="1920" height="1080" alt="457677959-84ca91c6-7b8d-4e0d-b604-7bbccf27c982" src="https://github.com/user-attachments/assets/ba6e0774-2fdf-42b7-9813-390d575b9283" />
<img width="1920" height="1080" alt="457677981-602d1ec2-c5ac-4a8b-a3c2-a74d243b5538" src="https://github.com/user-attachments/assets/da3a4e87-3e8a-4a07-a50a-cc5db915eb1a" />

Once finished, you’ll find a folder named `Dumpling` at the root of your SD card, containing:

```
 💾 SD:/
 ├─ 📂 Dumpling/
 │  ├─ 📂 Games/
 │  │  ├─ 📂 Breath of the Wild/
 │  │  │  ├─ 📜 ...
 │  ├─ 📂 Updates/
 │  │  ├─ 📂 Breath of the Wild/
 │  │  │  ├─ 📜 ...
 │  ├─ 📂 DLCs/
 │  │  ├─ 📂 Breath of the Wild/
 │  │  │  ├─ 📜 ...
```

Copy the entire `Dumpling` folder to a memorable location on your PC, e.g., `C:/Games/WiiU`.

---

## Optional – Installing Cemu

If you plan to play on PC, you'll need **Cemu**, a Wii U emulator. Follow [this installation guide](https://cemu.cfw.guide/installing-cemu.html), which walks you through downloading, optimizing, and configuring the emulator for *Breath of the Wild*.

Avoid YouTube tutorials, most are outdated or inaccurate.

**Common Cemu Mistakes to Avoid:**
- Do **not** use version 2.0, as it’s experimental and unstable. Use version **2.1+** or 1.26.2f.
- In BotW's graphic packs under the `Mods` section make sure to ENABLE Extended Memory and **DISABLE Draw Distance**.

---

## Setting Up UKMM

**UKMM** is the successor to **BCML**, developed by the same team. It’s faster, more stable, and actively maintained.

1. Download the latest release from [GitHub](https://github.com/GingerAvalanche/ukmm/releases/latest). As of now, the latest version is `0.16.0`.
   - Choose the `.zip` (portable) or `.msi` (installer) for Windows.

2. Open UKMM. Go to the **Settings** tab before managing mods.

<img width="1794" height="1241" alt="457663358-3b8286ad-1313-4a5c-8c9e-8ba52e952af2" src="https://github.com/user-attachments/assets/2b1599c3-3d9f-4d83-a9b4-6fd9e4304651" />

   > 💡 Tip: If you close a window or tab by mistake, click `Window > Reset` in the top bar.

3. Under **Wii U Config**, use:
   - **Migrate from BCML** (if applicable).
   - Or click **Import Cemu Settings**, locate your `Cemu.exe`, and UKMM will handle configuration.

If these options don’t work, you can configure it manually.

<details>
<summary>Click to expand manual setup instructions</summary>

### Manual Configuration

1. Under **Wii U Config**, set your game language using the format `XXyy`, where:
   - `XX` = region (`EU`, `US`, `JP`)
   - `yy` = language (`en`, `fr`, etc.)

   Examples:
   - European English: `EUen`
   - American French: `USfr`

2. Configure game paths:
   - **Dump Type**: `Unpacked`
   - **Base Folder**: `.../Dumpling/Games/Breath of the Wild/content`
   - **Update Folder**: `.../Dumpling/Updates/Breath of the Wild/content`
   - **DLC Folder**: `.../Dumpling/DLCs/Breath of the Wild/content/0010`

3. **Deployment Settings**:
   - **Deploy Method**: `Copy` (console) or `Symlink (highly recommended)/Hard Links` (Cemu)
   - **Deploy Layout**: `With Named Folder`
   - **Output Folder**:
     - For Cemu:
       - v1.26.2f: `.../Cemu/graphicPacks` where `Cemu` is the folder containing your `Cemu.exe`
       - v2.1+: `C:/Users/YourUsername/AppData/Roaming/Cemu/graphicPacks`
     - For console: use a folder like `C:/ModPack`

</details>

Don’t forget to click **Save** before returning to the **Mods** tab.

---

## Installing Second Wind

1. Download the latest **UKMM-compatible** `.zip` of Second Wind from our [GitHub](https://github.com/CEObrainz/Second-Wind/releases/latest).  
   ⚠️ **Do not extract it**.

2. In UKMM, either drag-and-drop the `.zip` file or use `File > Open Mod...`.

3. Once loaded, **Second Wind** will appear in the mod list.  
   - If using other mods, drag Second Wind to the bottom of the list to give it **lowest priority (0)**.

4. Click **Apply**, and if **Auto-Deploy** is disabled, also click **Deploy**.

---

## Launching the Game with Mods

### For Cemu Users

1. Launch Cemu.
2. Right-click *BotW* > **Edit Graphic Packs**.
3. Ensure the `UKMM` mod pack appears under **Mods** and is enabled.

If it doesn’t show up, revisit the guide and double-check your paths and deployment method.

### For Console Users

1. Download and extract the latest versions of:
   - [Wii U Plugin Loader (nightly)](https://github.com/Maschell/WiiUPluginLoader/releases)
   - [WUPS Sdcafiine (nightly)](https://github.com/Maschell/SDCafiine/releases/tag/SDCafiine-WUPS-v1.4-nightly-67aa461)

2. Move the `wiiu` folders from both archives to the root of your SD card (merge the folders if asked).

3. On the SD card, create the following structure:

   ```text
   /sdcafiine/<BotW Title ID>/
   ```

   - Title IDs by region:
     - Europe: `00050000101C9500`
     - USA: `00050000101C9400`
     - Japan: `00050000101C9300`

4. Copy the `BreathOfTheWild_UKMM` folder (from your UKMM output directory) into the matching title ID folder above.

<details>
<summary>Click to view final mod layout</summary>

```text
 💾 SD:/
 ├─ 📂 sdcafiine/
 │  ├─ 📂 00050000101C9500 or 00050000101C9400 or 00050000101C9300/
 │  │  ├─ 📂 BreathOfTheWild_UKMM/
 │  │  │  ├─ 📂 aoc/
 │  │  │  │  ├─ 📜 ...
 │  │  │  ├─ 📂 content/
 │  │  │  │  ├─ 📜 ...
```

</details>

5. Reinsert the SD card into your console, boot it, and launch the **Homebrew Launcher**.

6. Open **Wii U Plugin Loader**, enable `Sdcafiine`, and press `+` to apply changes.  
   > 🔄 This must be done every time you power off the console.

7. Launch *Breath of the Wild*. When prompted, select the **BreathOfTheWild_UKMM** mod.

---

## Confirming the Mod is Working

- On the title screen, the logo should read **Second Wind**.
- If you installed the **Shrine Overhaul**, all shrines will feature new layouts.

## Troubleshooting

There may be instances where Second Wind does not seem to behave in an expected manner. In these situations please refer the [Troubleshooting and Bugs Channel within the Second Wind Hub Discord](https://discord.com/channels/600679859257081884/927264339264692284) for information on well-known issues.

Enjoy the enhanced *Breath of the Wild* experience!
