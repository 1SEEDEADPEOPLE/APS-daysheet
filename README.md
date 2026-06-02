# APS OnSite 📋

Health & Safety documentation app for APS Complete Property Services (NZ · Since 1991). Works as a Progressive Web App (PWA) — install directly on iPhone or Android from a browser, no app store needed.

---

## Document types

### 🟧 Day Sheet
Pre-start risk assessment for daily jobs.
- 18 standard hazards with tick/cross toggles
- Selectable PPE chips per hazard
- Custom hazard rows for non-standard risks
- On-screen signature capture (Leading Hand + Project Manager + team members)
- Photo attachments with captions
- Export as PDF or image

### 🟥 Incident Report
For near misses, accidents, or property damage. Submit within 24 hours.
- Injury and damage severity chips
- Witness details
- Investigation level selector (A / B / C) with Ian Gotty contact pre-filled for serious harm
- **Optional Toolbox Talk** — add a toolbox meeting record directly to the report, with individual member sign-off (mirrors the paper form exactly in the PDF export)
- Signature, photos, PDF export

### 🟦 Site Report
Photo inspection report (Roof / Leak / Custom).
- Add and caption photos
- Group related photos together with a shared title
- **Photo editor** — Crop tab (corner + edge handles) and Mark Up tab (pen, highlighter, arrow, rectangle, ellipse, text, eraser) with full undo, 10 colours + custom picker
- **Two-finger twist** to rotate any annotation object
- Drag-to-reorder photos in gallery view
- **Floating "Group selected" bar** — always reachable without scrolling
- Optional job details block (job number, client, address, date, author)
- Repositionable comment blocks (above or below photos)
- Three export options: full PDF · Photos-only PDF (for Upvise) · Single PNG image
- PDF layout: portrait photos pair 2-up (~4 per page), landscape photos go full-width (~2 per page)

---

## Shared features

- 💾 **Auto-save** — drafts save automatically as you type and the moment you close or background the app, so work is never lost
- 🔍 Searchable, filterable history ("Records") — search by job number or address
- 📞 Saved PM contacts with auto-complete; saved client list
- 🖊️ Save signatures for re-use
- 🌙 Light / dark / auto theme
- 📥 Backup & restore via JSON export
- 🔗 Web Share API with iOS fallback
- ✈️ Fully offline once installed

---

## Planned (future)

- SSSP (Site Specific Safety Plan)
- QR-code site sign-on

---

## Deploy to GitHub Pages

1. **Create a GitHub repository** (e.g. `aps-onsite`)
2. **Upload all files** to the repo root:
   - `index.html`
   - `sw.js`
   - `manifest.json`
   - `aps-logo.png`
   - `icon-180.png`
   - `icon-192.png`
   - `icon-512.png`
3. **Enable GitHub Pages:**  
   Settings → Pages → Source: "Deploy from a branch" → `main` / `(root)`
4. Visit `https://YOUR-USERNAME.github.io/REPO-NAME/`

---

## Install on phone

**iPhone (Safari):**
1. Open the GitHub Pages URL in Safari
2. Tap **Share** → **Add to Home Screen** → Add

**Android (Chrome):**
1. Open the URL in Chrome
2. Tap **⋮** → **Install app**

---

## Updating the app

1. Push updated files to GitHub (`index.html` + `sw.js` minimum)
2. Bump `CACHE_NAME` in `sw.js` (e.g. `v2.9.1` → `v3.0`) — this forces devices to fetch fresh files
3. Update `APP_VERSION` in `index.html` to match (shown in Settings → About)
4. Wait 1–2 minutes for Pages to deploy
5. On the phone: close the app fully, reopen — new version loads automatically

**If it doesn't update:** iPhone Settings → Safari → Advanced → Website Data → find the URL → swipe to delete → reopen.

**Rollback:** Settings → Pages → switch branch to a previous stable branch.

---

## Data & privacy

Everything stays on the user's device (IndexedDB via localForage). Nothing is sent to any server. Use **Settings → Export All Data** for backup.

---

## Tech stack

- Vanilla HTML / CSS / JS — single `index.html`, no build step
- [localForage](https://localforage.github.io/localForage/) — IndexedDB storage
- [signature_pad](https://github.com/szimek/signature_pad) — signature capture
- [jsPDF](https://github.com/parallax/jsPDF) + [html2canvas](https://github.com/niklasvh/html2canvas) — PDF generation
- Service worker for offline support and cache management

---

## Version history

| Version | Notes |
|---------|-------|
| v2.9.1 | Toolbox Talk per-member signatures; auto-save drafts |
| v2.9 | Site Report, photo editor (crop + mark up), two-finger rotate, floating group button, black-frame fix, orientation-aware PDF layout, build version in About |
| v2.x | Incident Report, history/records, theme toggle, backup/restore |
| v1.x | Day Sheet, signatures, PPE, PDF/image export |

---

Built for APS Complete Property Services · HSWA 2015 compliance
