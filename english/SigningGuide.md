## Additional Guide 5: Signing Mods — Automatic and Manual (Pro)

Every mod for Null's Brawl must be signed before it can be installed. There are two ways to sign: automatically (via the bot) and manually (via the #Signing Requests Pro topic).

### Automatic Signing (bot @nulls_mods_bot)

Suitable for simple mods consisting of a single JSON file (no resources).

**How to sign:**
1. Send your `.json` file to the bot in a private message (@nulls_mods_bot) or to the **#Signing Requests Lite** topic with the `/sign` command (you can also reply to a message containing the file).
2. Within seconds, the bot returns a signed file with the `.NullsBrawlAssets` extension.

**Limitations of automatic signing:**
- The mod must consist only of `content.json` (no textures, sounds, icons).
- The signed file is valid for only **3 days**; after that it cannot be installed.
- The `@author` field is filled automatically with your nickname and Telegram ID (cannot be changed).
- UUID is generated automatically based on `@author` + `@title` (constant for the same pair).
- An icon (`icon.png`) is not supported.

**When to use:** for quick testing or sharing with friends (considering the 3‑day validity).

### Manual Signing (Pro)

Suitable for any mod, especially those containing resources (textures, music) and intended for publication in the library.

**Process:**
1. Prepare a ZIP archive containing:
   - `content.json` (required)
   - all necessary resource files (in appropriate folders: `sc3d`, `sfx`, `music`, etc.)
   - optionally: `icon.png` (square PNG, not larger than 640×640)
2. Make sure the files are in the archive root, not inside an intermediate folder.
3. Generate a UUID (see Guide 4) and write it down. For a new mod, the UUID must be unique; for an update, it must match the previous one.
4. Send the archive to the **#Signing Requests Pro** topic.
5. In the message, you **must** provide:
   - **Mod name**
   - **Description** (briefly what the mod does)
   - **UUID** (as `UUID: ...`)
   - **Version** (for updates, e.g., `@version: 1.1.0`)
   - Links to screenshots/videos (if any) — they must point to messages in @nb_mods.
6. Wait for volunteers to review and sign the mod. This may take from a few hours to several days.

**Requirements for Pro signing:**
- The mod must follow the rules (see the main guide).
- The name and description should be meaningful, error‑free, and preferably localised into Russian and English.
- Icon (if any) — only PNG, square, ≤640×640.
- Using someone else’s UUID without permission is prohibited.
- If updating, the version must be higher than the previous one.

**Publishing to the library:**
If you want your mod to be added to the library, add the phrase “Please add to library” in your message. The mod must introduce serious changes (not just replacing one track).

### Pre‑submission Checks

- Validate `content.json` (e.g., at https://jsonlint.com).
- All file paths are correct.
- UUID is valid.
- For mods with features, ensure there are no conflicts (e.g., in a RADIO_GROUP, no more than one feature is enabled by default).