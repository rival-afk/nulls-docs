## Additional Guide 6: Testing Mods Without Signing

During development, you don’t need to sign your mod every time. Null's Brawl provides a special client and the ability to load mods from folders.

### Method 1: Special Developer APK

Starting from version 65.165, a separate APK exists that allows loading unsigned mods (directly from ZIP or JSON).

**Where to download:**  
The link to the current version appears in announcements (e.g., https://tempweb.nullsusercontent.com/fpapk/nb_65.165_release_412b740e.apk?allowUnsignedMods=1).

**Important:** this APK is intended **only for developers**. Use it to test your own mods. Installing unsigned mods made by others is forbidden. Violation may lead to account blocking.

### Method 2: Manual Installation via Folders (for any client)

This method works in the regular Null's Brawl as well, but requires the mod to be unpacked into a specific folder.

**Step‑by‑step:**
1. **Create a mods folder**  
   In the device’s internal storage, create a folder, e.g., `NullsBrawlMods`.

2. **Generate a UUID** for your mod at https://uuidgenerator.net. Copy it.

3. **Create a subfolder named with the UUID**  
   Inside `NullsBrawlMods`, create a folder whose name exactly matches the generated UUID.

4. **Unpack the mod** into that subfolder.  
   - If you have a ZIP archive, extract its contents directly into the UUID folder.
   - If you only have `content.json`, rename it to `content.json` (if it has a different name) and place it in the UUID folder. Any resource files should also be placed there, in appropriate subfolders (e.g., `sc3d`).

5. **Add the folder to the mod loader**  
   - Open Null's Brawl.
   - Go to mod settings (gear icon).
   - Click **“Add folder”**, select the `NullsBrawlMods` folder.
   - Confirm usage and grant permission.

6. **Restart the game**  
   Close the game completely and reopen it. Your mod should appear in the list. Enable it.

**Important:** after adding the folder once, you don’t need to repeat step 5 for new mods — just create new subfolders with UUIDs and put the files there. They will appear in the list on the next game launch.

**Screenshots of the process:** https://t.me/nb_mods/1/118704

### Method 3: Nulls TestMods Utility (by darkmean)

There is an unofficial utility that automates the process of installing mods for testing.

**How to use:**
1. Download and install the Nulls TestMods app (search in the chat).
2. Grant file access permissions.
3. In a file manager or Telegram, select your `.zip` or `.json` file and open it with “Nulls TestMods”.
4. The utility will create the `NullsBrawlMods` folder and unpack the mod with the correct UUID.
5. Then in Null's Brawl, add the `NullsBrawlMods` folder (if not already added) and enable the mod.

**Limitations:** currently does not support `.toml` files.

**Note:** this is a third‑party tool, not associated with Null's Team. Use it at your own risk, only for your own mods.