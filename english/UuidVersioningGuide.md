## Additional Guide 4: UUID and Versioning of Mods

Proper use of UUID and version numbers helps users automatically update mods and avoid conflicts.

### UUID (Modification-Id)

**For signed mods (.NullsBrawlAssets):**  
The UUID is specified in the `META-INF/MANIFEST.MF` file under the `Modification-Id` field.

**For unpacked mods (folders):**  
The UUID is determined by the folder name. Create a folder with a name matching the UUID and place the mod files inside.

**Why is UUID needed?**
- If a user installs a mod with the same UUID, the old mod is automatically removed. This simplifies updating.
- UUID is used to identify the mod in the system and in the library.

**How to generate a UUID?**
- Online generators: https://www.uuidgenerator.net
- Command line: `uuidgen` (Linux/macOS) or PowerShell: `[guid]::NewGuid()`

**Rules:**
- UUID must be unique for each new mod.
- When updating a mod, the UUID must stay **the same**.
- Never use someone else's UUID without the author's permission.

### Versioning (@version)

The mod version is specified in `content.json` with the `@version` key. The format is a string `X.Y.Z`, where X, Y, Z are non-negative integers (e.g., `"1.0.0"`). If the field is missing, `"1.0.0"` is assumed.

**Meaning of numbers (SemVer):**  
The SemVer scheme is commonly used:
- **X (major)** — major version. Changes with large, conceptual updates.
- **Y (minor)** — minor version. Adding new features that don't break compatibility.
- **Z (patch)** — patch. Bug fixes, small adjustments.

**Important:** strict SemVer compliance is not required. The main rule is: the new version's numbers (from left to right) must be greater than the previous version's. For example:
- `1.0.0` → `1.0.1` → `1.1.0` → `2.0.0`
- `1.9.5` → `1.9.6` or `1.10.0` or `2.0.0`

**Comparing versions:**
The mod loader considers the version with a larger higher-order number as newer. For example, `2.0.0` is newer than `1.99.99`.

### Usage in the Library

- In the library, mods are sorted and the user sees the latest version.
- Automatic signing via the bot generates a UUID based on `@author` + `@title`, so it stays constant for the same mod.

**Proper update example:**
- Version 1.0.0: first release.
- Version 1.1.0: new feature added.
- Version 1.1.1: bug fixed.
- Version 2.0.0: completely overhauled mod.
