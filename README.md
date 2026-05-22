# APS OnSite 📋

Health & Safety documentation app for APS Complete Property Services. Works as a Progressive Web App (PWA) - install on iPhone or Android directly from a browser, no app store needed.

## What's in it

### Current document types:
- **📝 Day Sheet** - Pre-start risk assessment for small one-day jobs (the original)
- **⚠️ Incident Report** - Near miss, accident or damage reports (submit within 24hrs)

### Planned (future):
- SSSP (Site Specific Safety Plan) - bigger projects
- Roof / Leak Report - inspection reports
- More as needed

## Features

- ✅ Tick/cross hazard toggles with selectable PPE chips
- ➕ Custom hazard rows for non-standard risks
- 🖊️ On-screen signature capture with "save signature" for regulars
- 📞 Saved PMs auto-fill phone numbers, saved Clients in dropdown
- 📷 Photo attachments with captions
- 📄 Export as PDF or 🖼️ image (with native share sheet)
- 💾 Works fully offline once installed
- 🔍 Searchable, filterable history of all your documents
- 📥 Backup/restore via JSON export

## Setup - Deploy to GitHub Pages

1. **Create a new GitHub repository** (e.g. `aps-onsite`)
2. **Upload all the files** to the repo root:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-180.png`
   - `icon-192.png`
   - `icon-512.png`
3. **Enable GitHub Pages:**
   - Settings → Pages → Source: "Deploy from a branch" → main / root
4. Visit `https://YOUR-USERNAME.github.io/aps-onsite/`

## Install on Phone

**iPhone (Safari):**
1. Open the GitHub Pages URL in Safari
2. Tap the **Share** button → **Add to Home Screen** → Add

**Android (Chrome):**
1. Open the URL in Chrome
2. Tap the **⋮ menu** → **Install app**

## Updating the App

Push new files to GitHub, increment the `CACHE_NAME` in `sw.js` (e.g. `v7` → `v8`), wait 1-2 minutes for Pages to deploy, then on the phone:
1. Close the app fully (multitask view → swipe up)
2. Reopen - new version loads automatically thanks to the cache version bump

If it doesn't update: iPhone Settings → Safari → Advanced → Website Data → find the URL → swipe to delete → reopen app.

## Data Storage

Everything stays on the user's device (IndexedDB). Nothing is sent anywhere. Use **Settings → Export All Data** for backup.

## Tech

- Vanilla HTML/CSS/JS - no build step
- [localForage](https://localforage.github.io/localForage/) for IndexedDB
- [signature_pad](https://github.com/szimek/signature_pad) for signatures
- [jsPDF](https://github.com/parallax/jsPDF) + [html2canvas](https://github.com/niklasvh/html2canvas) for PDF generation
- Service worker for offline support

---

Built for APS Complete Property Services · HSWA 2015 compliance
