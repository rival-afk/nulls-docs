## Additional Guide 5: TOML Format and ZIP Preparation

### TOML Format (Alternative to JSON)

The bot @nulls_mods_bot accepts files in TOML format (extension `.toml`). The structure is similar to JSON, but the syntax is more concise and readable.

**Example content.toml:**
```toml
"@title" = "No Outline"
"@description" = { RU = "Убирает обводку у скинов", EN = "Removes outline from skins" }
"@version" = "1.0.0"

[skins."*"]
OutlineShader = "sc3d/shaders/impostor"
```

**Advantages of TOML:**
- Fewer brackets and quotes.
- More readable structure.
- Convenient for simple mods.

**What happens during signing:**  
When signing, the bot automatically converts TOML to JSON inside the `.NullsBrawlAssets`. You don't need to worry about conversion.

**Limitations:**
- Not all JSON features are available in TOML (e.g., complex nested structures with arrays may require special syntax).
- If you use advanced features, you may need to switch back to JSON.

### Preparing ZIP Archive Before Submission

Before submitting your mod for signing, make sure the archive is assembled correctly.

**Correct ZIP structure:**
Files must be in the archive root, not inside a folder.

Correct:
```
mod.zip
├── content.json (or content.toml)
├── icon.png
├── sc3d/
└── sfx/
```

Incorrect (extra folder):
```
mod.zip
└── mymod/
    ├── content.json
    └── ...
```

**Checklist before submission:**
1. `content.json` or `content.toml` is in the archive root.
2. Icon file `icon.png` is present (if required).
3. Resources (`sc3d/`, `sfx/`, `textures/`, etc.) are in the root or in appropriate subfolders.
4. No extra wrapper folders in the archive.
5. The archive is not corrupted and opens with standard tools.

### Icon Generation

If you don't have an icon for your mod, you can generate one at https://icon.kitchen. Choose a suitable style, colors, and size — you'll get a square PNG of the required size.

**Recommended size:** 512x512 pixels.
