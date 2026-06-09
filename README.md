# FIFA World Cup 2026 Dashboard

A live dashboard for tracking the FIFA World Cup 2026 — schedules, group standings, scores, bracket, and TV broadcaster info.

🔗 **[https://gustavzet.github.io/vm2026-dashboard/](https://gustavzet.github.io/vm2026-dashboard/)**

---

All credit goes to [TAkustik](https://github.com/TAkustik/wm2026-dashboard) for building the original dashboard. This fork includes a number of improvements, bug fixes, and new features described below — developed with the help of [Claude](https://claude.ai) by Anthropic.

---

## Changes & Improvements

### 🌍 Language & Localisation
- **English is now the default language** (was German)
- **Swedish (`sv`) added as a supported language**, with full translations for all UI strings, team names, round labels, and date formatting
- All hardcoded German text in `index.html` removed — page title, settings panel labels, tab names, filter buttons, section headings, footer hint, and the `<html lang>` attribute are all now in English

### 📺 Separate TV Region Setting
- Added an independent **TV Region** selector in settings, decoupled from the favourite team country
- Previously, choosing your favourite team also determined which TV broadcasters were shown — now you can follow Sweden while seeing German or UK broadcaster info, for example
- TV Region is saved to `localStorage` and also supports a `?tv=XX` URL parameter (useful for Home Assistant dashboard cards)

### 🐛 Bug Fixes
- **Sweden (SE)** had `teamCode: null, group: null` — fixed to `teamCode: 'SE', group: 'F'`, so filtering and the Favourite tab now work correctly
- **Turkey (TR)** had the same issue — fixed to `teamCode: 'TR', group: 'D'`
- **Czech Republic (CZ)** was missing entirely from `countryConfig` despite being in the tournament (Group A) — added with correct broadcasters (ČT Sport / Nova)
- **8 tournament teams were missing** from the country selector dropdowns entirely: Bosnia & Herzegovina, Haiti, Scotland, Cape Verde, Norway, Algeria, Jordan, DR Congo — all added with `countryConfig` entries and broadcaster info

### 🗂 Country Dropdowns
- Both the **Favourite Country** and **TV Region** dropdowns are now **sorted alphabetically within each region**
- All 48 tournament teams are now present and selectable