## Additional Guide 4: UUID and Versioning of Mods

Proper use of UUID and version numbers helps users automatically update mods and avoid conflicts.

### UUID (Modification-Id)

Every mod must have a unique identifier in UUID format. It is specified in the `META-INF/MANIFEST.MF` file under the `Modification-Id` field.

**Why is UUID needed?**
- If a user installs a mod with the same UUID, the old mod is automatically removed. This simplifies updating.
- UUID is used to identify the mod in the system and in the library.

**How to generate a UUID?**
- Online generators: https://www.uuidgenerator.net
- Command line: `uuidgen` (Linux/macOS) or PowerShell: `[guid]::NewGuid()`

**Rules:**
- UUID must be unique for each new mod.
- When updating a mod, the UUID must stay **the same**.
- Never use someone else’s UUID without the author’s permission.

### Versioning (@version)

The mod version is specified in `content.json` with the `@version` key. The format is a string `X.Y.Z`, where X, Y, Z are non‑negative integers (e.g., `"1.0.0"`). If the field is missing, `"1.0.0"` is assumed.

**Meaning of numbers:**
- **X (major)** — major version. Changes with large, conceptual updates.
- **Y (minor)** — minor version. Adding new features that don’t break compatibility.
- **Z (patch)** — patch. Bug fixes, small adjustments.

**Version update rules:**
- When the major version (X) changes, all lower numbers (Y, Z) must be reset to zero: `1.9.5` → `2.0.0`.
- When the minor version (Y) changes, the patch (Z) resets to zero: `1.8.5` → `1.9.0`.
- The patch simply increments: `1.0.0` → `1.0.1`.

**Comparing versions:**
The mod loader considers the version with a larger higher‑order number as newer. For example, `2.0.0` is newer than `1.99.99`.

### Usage in Signing and the Library

- For manual signing (Pro) you must specify the UUID and version (for updates) in your request.
- In the library, mods are sorted and the user sees the latest version.
- Automatic signing via the bot generates a UUID based on `@author` + `@title`, so it stays constant for the same mod.

**Proper update example:**
- Version 1.0.0: first release.
- Version 1.1.0: new feature added.
- Version 1.1.1: bug fixed.
- Version 2.0.0: completely overhauled mod.