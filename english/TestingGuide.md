## Additional Guide 6: Testing Mods Without Signing

During development, you don't need to sign your mod every time. Null's Brawl provides a special developer APK that allows loading mods directly from ZIP, JSON, or TOML files.

### Method 1: Special Developer APK

Starting from version 65.165, a separate APK exists that allows loading unsigned mods.

**Where to download:**  
The link to the current version is published in announcements in the hvh Telegram channel (https://t.me/hvh). Look for messages mentioning "developer APK".

**Important:** this APK is intended **only for developers** to test their own mods. Installing unsigned mods made by others is forbidden and may lead to account blocking.

### Method 2: Nulls TestMods Utility (by darkmean)

There is an unofficial utility that automates the process of installing mods for testing.

**How to use:**
1. Download and install the Nulls TestMods app (link available in the modders' chat).
2. Grant the app file access permissions.
3. In a file manager or Telegram, select your `.zip`, `.json`, or `.toml` file and open it with "Nulls TestMods".
4. The utility will create the `NullsBrawlMods` folder in internal storage and unpack the mod with the correct UUID.
5. In Null's Brawl, add the `NullsBrawlMods` folder via mod settings (gear icon → "Add folder") if you haven't already.
6. Enable the mod in the list and restart the game.

**Limitations:** the utility automatically generates a UUID based on the mod name, but for precise control it's better to specify the UUID manually in the folder structure.

**Note:** this is a third-party tool, not associated with Null's Team. Use it only for testing your own mods.

### Method 3: Manual Installation via Folders (developer APK only)

This method works **only in the developer APK** from Method 1. Folder loading is not available in the regular client.

**Step-by-step:**
1. Create a mods folder in internal storage, e.g. `NullsBrawlMods`.
2. Generate a UUID for your mod (see the UUID guide).
3. Inside the mods folder, create a subfolder with a name that exactly matches the UUID.
4. Unpack the mod files (`content.json`, resources, etc.) directly into the UUID folder.
5. In the developer APK, open mod settings (gear icon) → "Add folder" → select `NullsBrawlMods`.
6. Restart the game — your mod will appear in the list.

**Important:** once you've added the folder, you don't need to repeat this for new mods. Just create new subfolders with UUIDs and they will automatically appear in the list on the next game launch.
