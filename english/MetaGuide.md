## Additional Guide 1: Meta Information in Mods (Title, Description, Author, Localization, HTML)

The `content.json` file contains three mandatory fields that control how the mod is displayed: `@title`, `@description`, and `@author`. They can be plain strings or support localization and HTML formatting.

### Required Fields

```json
{
  "@title": "Mod Title",
  "@description": "Mod Description",
  "@author": "Author"
}
```

- `@title` — the name of the modification. It should be short and clear.
- `@description` — a description of what the mod does. Try to mention specific changes.
- `@author` — the name or nickname of the developer.

### Localization (Multi‑language Support)

To make the mod understandable for users from different countries, these fields can be translated into multiple languages. Instead of a string, use an object where the key is a two‑letter language code (ISO 639, uppercase) and the value is the text in that language.

The key `EN` (English) is mandatory — it will be used when the user’s language is not present in the dictionary.

**Example:**
```json
{
  "@title": {
    "RU": "Супер мод",
    "EN": "Super mod",
    "TR": "Süper mod"
  },
  "@description": {
    "RU": "Добавляет крутые скины",
    "EN": "Adds cool skins"
  },
  "@author": "Your nickname"
}
```

Any language supported by Android can be used: RU, EN, TR, ZH, ES, DE, FR, etc.

### HTML Formatting

The `@title`, `@description`, and `@author` fields can contain HTML tags for better formatting: bold text, links, lists, etc.

**Available tags** (based on `android.text.Html`):
- `<b>bold</b>`
- `<i>italic</i>`
- `<u>underlined</u>`
- `<s>` or `<del>` — strikethrough
- `<font color='#RRGGBB'>colored text</font>`
- `<a href='URL'>link</a>`
- `<br>` — line break
- `<ul><li>list item</li></ul>`
- `<p>`, `<div>`, `<span>`, `<cite>`, `<blockquote>`, `<big>`, `<small>`, `<tt>`, `<code>`, `<sup>`, `<sub>`, `<h1>…<h6>`

**Important:** remember to escape quotes inside JSON.

**Example with HTML:**
```json
{
  "@title": "<b>Super mod</b>",
  "@description": "<p>Description:</p><ul><li><i>Cool feature</i></li><li><u>Another one</u></li></ul><br>Link: <a href='https://t.me/nb_mods'>Chat</a>",
  "@author": "<a href='https://t.me/danyanull'>danyanull</a>"
}
```

### Recommendations

- Start sentences with a capital letter, put spaces after punctuation marks.
- Avoid transliteration (write "default", not "дефолтный").
- The description should be meaningful: answer the questions “What will change?” and “How will it affect the game?”.
- For long descriptions, HTML can help structure the information.