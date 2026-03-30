# How to Start Creating Mods for Null's Brawl?

### Join Our Chat and Install the Special Client

Currently, all important discussions regarding modifications and their development take place in the Telegram chat: [t.me/nb_mods](https://t.me/nb_mods).

There, in the #Announcements section, you will also be able to download a special APK. Install it to unlock the next step.

### Create a Mods Folder

Create an empty folder with any name on the external storage. For example, NBMods.

Open Null's Brawl, go to the mod loader settings, and select this folder as the external source.

### Create Your First Mod

Each new mod must have its own unique ID in UUID format. Go to the website [uuidgenerator.net](https://uuidgenerator.net) to generate one.

Navigate to the mods folder you created in the previous step. Inside it, create another folder whose name exactly matches the generated UUID of the mod.
This folder is now your mod's folder.

Inside it, create a file named **content.json** (lowercase — this is important). Place the following code inside this file:

```json
{
  "@title": "My First Mod",
  "@description": "And its description",
  "@gv": 65,
  "en": {
    "TID_JESTER": {
      "EN": "CLOWN"
    }
  }
}
```

<details>
<summary>
How the file and folder structure should look
</summary>

```
╔ External storage
╚╦ 📁 NB Mods
 ╚╦ 📁 bd850738-67cb-4583-92c4-a12f4f6080d1
  ╚═ 📝 content.json
```

But this is just an example. Folders can be named differently.
</details>

### Enable Your First Mod and Test It

Open Null's Brawl, go back to the mod loader settings, and you should see your modification in the list of mods.

Enable it and return to the game. If everything is done correctly, Chester will now be named "CLOWN".

### Where to Get the Latest Table Files?

Game table files (CSV) are not stored in this repository because they are frequently updated. To get the latest version:

1. **Telegram channel hvh:** the channel https://t.me/hvh periodically publishes archives with table files for the current game version.
2. **Extract from APK:** you can extract table files directly from the game's APK file using an archiver (they are located in the `assets/csv` folder).

**Important:** do not commit CSV files to documentation repositories — they become outdated with every balance update or new game version.

### Next Steps

To create more complex mods, you should:

1. Learn how the game's files are structured;
2. Study the [mod format](Format.md) in more detail.
