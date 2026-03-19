# ZonePeek

A Chrome extension for checking local times across multiple cities. Open the popup, see all your clocks.

---

## Motivation

Most world clock extensions have limited city coverage and run background processes that consume battery even when idle. ZonePeek covers **4,000+ cities** using the full IANA timezone database and has **no background script** — nothing runs when the popup is closed.

---

## Features

- Fuzzy city search (typo-tolerant) via Fuse.js
- Persistent city list saved with `chrome.storage.local`
- Live 1-second clock updates, active only while popup is open
- UTC offset relative to local time (+9h, −13h, etc.)
- Country flag auto-display
- Drag-to-reorder city cards
- 24h / 12h toggle, dark / light / system theme

---

## Stack

| | |
|---|---|
| Platform | Chrome Extension — Manifest V3 |
| Language | Vanilla JS (ES2022+) |
| Timezone | `Intl.DateTimeFormat` — browser-native, no library |
| Search | Fuse.js (~24 KB) |
| Storage | `chrome.storage.local` |
| Font | Playwrite IT Moderna (Google Fonts) |

---

## Project Structure

```
zonePeek/
├── manifest.json
├── popup/
│   ├── popup.html
│   ├── popup.js
│   └── popup.css
├── data/
│   └── cities.json       # ~4,000 cities (GeoNames, population 15,000+)
├── lib/
│   └── fuse.min.js
└── icons/
```

---

## Permissions

`storage` — Save and restore city list and user preferences.
No host permissions. No network requests. No tracking.
