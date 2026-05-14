# APS Day Sheet 📋

A Progressive Web App for completing pre-start risk assessments digitally. Replaces the paper "Pre-Start Risk Assessment" form for APS Complete Property Services.

Works offline, installs to your phone's home screen, and exports both PDF and image versions of completed day sheets.

## Features

- ✅ Tick/cross hazard toggle for all 18 standard hazards from the APS form
- ➕ 2 extra blank rows for custom hazards
- 🖊️ On-screen signature capture with "save signature" option for regulars
- 📷 Photo attachments with captions (appended to PDF on extra pages)
- 📄 Export as PDF or 🖼️ image (for iPhone-to-Android sharing where PDFs get blocked)
- 💾 Saves to device, works fully offline once installed
- 🔍 Searchable history of previous day sheets
- 📥 Backup/restore via JSON export

## Setup - Deploy to GitHub Pages

Easiest way to host it for free so your crew can install it on their phones:

1. **Create a new GitHub repository** (e.g. `aps-daysheet`)
2. **Upload all the files** from this folder to the repo root:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
3. **Enable GitHub Pages:**
   - Go to your repo's **Settings** → **Pages**
   - Under **Source**, pick **Deploy from a branch**
   - Choose `main` branch and `/ (root)` folder
   - Click **Save**
4. Wait 1-2 minutes, then visit `https://YOUR-USERNAME.github.io/aps-daysheet/`

## Install on Phone

**iPhone (Safari):**
1. Open the GitHub Pages URL in Safari
2. Tap the **Share** button (square with arrow)
3. Scroll down and tap **Add to Home Screen**
4. Tap **Add**

**Android (Chrome):**
1. Open the URL in Chrome
2. Tap the **⋮ menu** in the top right
3. Tap **Install app** (or **Add to Home Screen**)
4. Tap **Install**

Once installed it'll run like a regular app — full screen, works offline, no browser bar.

## Updating the App

Push your changes to GitHub. Next time anyone opens the app it'll fetch the new version automatically (might need to close and reopen once).

## Data Storage

All data stays on the user's device — nothing is sent anywhere. Use **Settings → Export All Data** to back up day sheets to a JSON file. If someone clears their browser data or changes phones, they can restore from that backup.

## Tech Stack

- Vanilla HTML/CSS/JS — no build step needed
- [localForage](https://localforage.github.io/localForage/) for IndexedDB storage
- [signature_pad](https://github.com/szimek/signature_pad) for signatures
- [jsPDF](https://github.com/parallax/jsPDF) + [html2canvas](https://github.com/niklasvh/html2canvas) for PDF generation
- Service worker for offline support

## Customising

To tweak hazard wording or add new standard rows, edit the `HAZARDS` array near the top of the `<script>` block in `index.html`.

To change the colour scheme, edit the CSS variables at the top of the `<style>` block (look for `:root { --aps-red: ... }`).

## Troubleshooting

- **PDF won't generate** — make sure the page is fully loaded and there are no broken images (deleted photos etc.)
- **Photos look low-res** — they're compressed to 1600px max dimension to keep PDFs sendable. Edit the `resizeImage` call in `index.html` if you need higher resolution.
- **App not updating after push** — close the app fully, reopen. If that doesn't work, in browser go to Settings → clear site data for the URL.
- **Lost data** — use the export backup feature regularly. Browser data can be cleared by system cleanup, low storage warnings etc.

---

Built for APS Complete Property Services · HSWA 2015 compliance helper
