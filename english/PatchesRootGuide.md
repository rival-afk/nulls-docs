## Additional Guide 3: Advanced Patching — @patches and @root

For easier maintenance of large mods, two keys are introduced: `@patches` (to move table patch descriptions to an external file) and `@root` (to specify a folder containing resources). They can be used both at the mod root and inside individual features.

### @patches

Allows you to move a JSON object with table patches to a separate file. This keeps `content.json` cleaner, especially for large mods.

**Syntax:**
```json
{
  "@patches": "path/to/file.json"
}
```
The path is relative to the root of the mod archive (ignores `@root`).

**Example:**
Instead of writing all patches inside `content.json`:
```json
{
  "@title": "My mod",
  "skins": { ... },
  "skin_confs": { ... }
}
```

Create a file `patches/skins.json`:
```json
{
  "skins": { ... },
  "skin_confs": { ... }
}
```
And in `content.json` specify:
```json
{
  "@title": "My mod",
  "@patches": "patches/skins.json"
}
```

**Important:** if `@patches` is used, it is **forbidden** to specify any other patches (e.g., `"skins": {...}`) in the same object — they will be ignored, and the mod won't be signed.

`@patches` can be used both in the mod root and inside a feature. Inside a feature it works the same way.

### @root

Specifies a folder inside the archive that contains all the mod's resources (textures, sounds, models). This allows you to organise files neatly, instead of dumping everything in the root.

**Syntax:**
```json
{
  "@root": "folder_name"
}
```

**Example:**
If your archive has a folder `my_res` with standard subfolders `sc3d`, `sfx`, etc., setting `"@root": "my_res"` makes the game look for files relative to `my_res`, not the archive root.

**Note:** in some versions (e.g., 63.286) `@root` might not work. Starting from `@gv:64` it works properly. Check compatibility.

`@root` also works inside a feature: then resources from that folder are loaded only when the feature is enabled.

### Combined Usage

You can combine `@patches` and `@root`. For example:
```json
{
  "@title": "Large mod",
  "@root": "assets",
  "@features": {
    "feature1": {
      "@name": "Feature 1",
      "@root": "feature1_res",
      "@patches": "patches/feature1.json"
    }
  }
}
```

### Notes

- Paths in `@patches` are always relative to the archive root, regardless of `@root`.
- If you use `@root` for a feature, make sure the specified folder exists in the archive.