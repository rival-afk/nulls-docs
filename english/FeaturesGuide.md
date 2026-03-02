## Additional Guide 2: Features (@features) and Feature Groups (@feature_groups)

Features allow splitting a mod into independent toggle‑able parts. The user can choose which functions of the mod to activate. Feature groups let you combine related features and define the selection type (single choice from a group or multiple choices).

### @features

In the root object of `content.json` you can add the `@features` field. Its value is an object where the key is a feature identifier (arbitrary string) and the value is an object with the feature’s settings.

**Feature structure:**
'''json
"@features": {
  "feature_id": {
    "@name": "Feature name (required)",
    "@description": "Feature description (optional)",
    "@enabled": true,           // enabled by default? (defaults to true)
    "@conflicts": ["other_feature"], // list of feature IDs that cannot be enabled simultaneously with this one
    "@root": "resources_folder",    // not working in older versions
    "@patches": "path/to/file.json", // external file with patches (see Guide 3)
    // then you can put any table patches, just like in the mod root (e.g., "skins": {...})
  }
}
'''

**Simple feature example:**
'''json
{
  "@title": "Mod with features",
  "@features": {
    "extra_skins": {
      "@name": "Extra skins",
      "@description": "Adds a set of skins for Colt",
      "@enabled": true,
      "skins": {
        "Colt_skin": { "Character": "Colt", "Model": "colt_gold.scw" }
      }
    },
    "custom_music": {
      "@name": "Different music",
      "@enabled": false,
      "music": { "lobby": "mymusic.mp3" }
    }
  }
}
'''

### @feature_groups

Groups combine several features into a single visual block in the mod settings. You can define the group type:
- `DEFAULT` (default) — ordinary checkboxes, several features from the group can be enabled.
- `RADIO_GROUP` — radio buttons, only one feature from the group can be selected.

**Syntax:**
'''json
"@feature_groups": {
  "group_id": {
    "@name": "Group name (required)",
    "@description": "Group description (optional)",
    "@type": "RADIO_GROUP", // or "DEFAULT"
    "@features": ["feature_id1", "feature_id2", ...]
  }
}
'''

**Important for RADIO_GROUP:** among the listed features, no more than one should be enabled by default (otherwise the mod won’t be signed).

**Full example with a group:**
'''json
{
  "@title": "Mode selection",
  "@features": {
    "mode_easy": {
      "@name": "Easy mode",
      "@enabled": true
    },
    "mode_hard": {
      "@name": "Hard mode",
      "@enabled": false
    }
  },
  "@feature_groups": {
    "difficulty": {
      "@name": "Difficulty",
      "@description": "Choose the difficulty level",
      "@type": "RADIO_GROUP",
      "@features": ["mode_easy", "mode_hard"]
    }
  }
}
'''

### Mod Loading Order

1. First, the root elements of `content.json` (all patches outside features) are loaded. They are always active.
2. Then all enabled features are loaded sequentially, in the order they appear in `@features`. If a feature overrides some data, the later feature takes priority.

This allows you to put common data in the root and specific data in features, without worrying about dependencies.

### Restrictions

- Inside a feature you can use `@patches` and `@root` (see the next guide).
- You cannot specify both `@patches` and nested patches inside the feature body — only one of them.