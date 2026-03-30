## Additional Guide 7: Tools for Mod Makers

To make mod creation and debugging easier, the community has developed several useful tools.

### 1. JSON Schema for Mods

An official JSON schema helps modern code editors (VS Code, IntelliJ IDEA) highlight errors, auto-complete keys, and show hints.

**How to enable:**
At the very beginning of your `content.json`, add the line:
```json
{
  "$schema": "https://ext.nulls.gg/mods/schema/schema.json",
  ...
}
```

After that, the editor will validate the file structure against the mod format.

**Documentation:**
https://ext.nulls.gg/mods/schema/docs

**Source code and suggestions:**
https://github.com/nulls-mods-community/schema

### 2. SC Editor (Editor for SC/SC2/SCTX Files)

SC Editor is a Java application for viewing and editing files in SC (2D textures and animations), SC2, and SCTX formats. It allows you to check your changes and even render objects into images/videos.

**Download:**
https://github.com/danila-schelkov/sc-editor/releases/latest

**Features:**
- Open SC, SC2, SCTX files.
- View contents.
- Save to the old SC format.
- Rendering (useful for content creators).

**Requirements:** Java (JRE). Works on Windows, MacOS, Linux.

### 3. JSON Validation

Always validate the syntax of your `content.json` before submitting for signing. Use https://jsonlint.com — just paste the text and click "Validate JSON".

### 4. Matrix Chat for Communication
If Telegram is unavailable, there is a Matrix server: https://matrix.to/#/#nbmods:dnull.xyz. You can use clients like Element X, FluffyChat. For users in Russia and China, the home server `dnull.xyz` is available.
