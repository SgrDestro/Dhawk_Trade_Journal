# Trade Journal PWA

A fully offline, installable web app for logging trades — covering both technical analysis and emotional state. All data stays on your device, stored in the browser's IndexedDB. No server, no account, no internet required after setup.

---

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire app — all HTML, CSS, and JavaScript in one file |
| `manifest.json` | Makes the app installable as a PWA (icon, name, colors) |
| `sw.js` | Service worker — enables offline use after first load |
| `icon-192.png` | App icon (home screen, small) |
| `icon-512.png` | App icon (splash screen, large) |

---

## Features

### Technical Journal
- Ticker, direction (Long / Short), entry price, exit price, share size
- Auto-calculated P&L
- Setup type: Breakout, Pullback, Reversal, Momentum, Range, News, Scalp, Other
- Free-form technical notes

### Emotional Journal
- Mood before and after the trade (5-point emoji scale)
- Confidence rating (1–5 slider)
- Emotion tags: FOMO, Fear, Greed, Revenge, Disciplined, Uncertain, Calm, Impulsive
- Free-form emotional notes

### Screenshots
- Attach chart screenshots to any trade entry
- Drag-and-drop or file browser upload
- Multiple images per trade supported
- Full-screen lightbox viewer
- Images are compressed automatically before storage

### Stats Dashboard
- Total trades logged
- Win rate
- Total P&L
- Average mood score

### Backup & Restore
- **Export**: Downloads all trades + screenshots as a dated `.json` file
- **Import**: Restores trades from any backup file; skips duplicates automatically
- Recommended: export every quarter and save to cloud storage or USB

---

## Setup & Installation

### Option 1 — GitHub Pages (recommended, free)
1. Create a free GitHub account at github.com
2. Create a new repository (e.g. `trade-journal`)
3. Upload all 5 files to the repository
4. Go to **Settings → Pages**, set source to `main` branch
5. Your app will be live at `https://yourusername.github.io/trade-journal`

### Option 2 — Local file (desktop only)
Open `index.html` directly in Chrome or Edge. Note: the service worker won't register over `file://`, so offline caching won't work, but the app itself functions normally.

### Installing on Android (Add to Home Screen)
1. Open the hosted URL in **Chrome for Android**
2. Tap the three-dot menu (⋮) in the top right
3. Tap **"Add to Home Screen"**
4. The app installs with its own icon and runs fullscreen, like a native app

### Installing on iPhone (Safari only)
1. Open the hosted URL in **Safari**
2. Tap the Share button (box with arrow)
3. Tap **"Add to Home Screen"**

---

## Data Storage

All data is stored in **IndexedDB** inside your browser — not in the cloud, not on any server. This means:

- Data persists across browser restarts and phone reboots
- Clearing your browser's site data will erase the journal
- Data does not sync between devices automatically — use the Export/Import backup to move data between devices

---

## Quarterly Backup Routine

1. Open the app
2. Click **⬇ Export** in the top right
3. Save the downloaded file (e.g. `trade-journal-backup-2026-05-06.json`) to:
   - Google Drive / iCloud / Dropbox, or
   - A USB drive or external hard disk
4. Keep the last 2–3 quarterly backups in case of file corruption

To restore on a new device or after data loss:
1. Open the app
2. Click **⬆ Import**
3. Select your backup `.json` file

---

## Browser Compatibility

| Browser | Supported |
|---|---|
| Chrome (Android & Desktop) | ✅ Full PWA support |
| Safari (iPhone & Mac) | ✅ Works, limited PWA features |
| Firefox | ✅ App works, no install prompt |
| Samsung Internet | ✅ Full PWA support |

---

## Privacy

This app has no analytics, no tracking, no ads, and makes no network requests after the initial page load. Your trading data never leaves your device.
