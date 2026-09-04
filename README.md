# ZwsCleanerTool 🧹

A small, dependency-free browser tool for detecting, explaining, and cleaning hidden or unusual Unicode characters.

Everything runs locally in the browser - entered text is never uploaded or sent to a server.

## Features

- Detects zero-width and invisible Unicode characters.
- Detects ASCII control characters while preserving normal tabs and line breaks.
- Detects bidirectional control characters.
- Removes unwanted characters such as Zero Width Space, Soft Hyphen, BOM and Word Joiner.
- Replaces non-breaking spaces with regular spaces.
- Replaces em dash, en dash and Unicode minus with `-`.
- Preserves Zero Width Joiner and Zero Width Non-Joiner instead of deleting them blindly.
- Shows Unicode code points, names, actions and character positions.
- Separates findings into **removed**, **replaced** and **preserved** categories.
- Uses the system theme by default and supports a manual light/dark theme switch.
- Uses no frameworks, external libraries, analytics or network requests.

## Privacy

ZwsCleanerTool is entirely client-side. The text you paste into the page stays in your browser and is processed only by JavaScript in `index.html`.

There is no backend, tracking, telemetry, analytics or third-party dependency.

## Cleaning rules

| Character | Action | Description |
| --- | --- | --- |
| `U+200B` | Remove | Zero Width Space |
| `U+FEFF` | Remove | Zero Width No-Break Space / BOM |
| `U+2060` | Remove | Word Joiner |
| `U+00AD` | Remove | Soft Hyphen |
| Bidi controls | Remove | Invisible direction-control characters |
| Unsafe ASCII controls | Remove | Except TAB, LF and CR |
| `U+00A0` | Replace | Non-breaking space → regular space |
| `U+202F` | Replace | Narrow no-break space → regular space |
| `U+2007` | Replace | Figure space → regular space |
| `U+2014` | Replace | Em dash → `-` |
| `U+2013` | Replace | En dash → `-` |
| `U+2212` | Replace | Minus sign → `-` |
| `U+200C` | Preserve | Zero Width Non-Joiner |
| `U+200D` | Preserve | Zero Width Joiner |

Normal line breaks (`LF` / `CR`) and tabs are preserved.

## Usage

Open `index.html` directly in a browser, or serve the repository as a static site.

No build step is required.

## Project structure

```text
ZwsCleanerTool/
├── index.html
├── README.md
└── LICENSE
```

## License

MIT
