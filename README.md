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
- **Promote to Incident Report or Leak Report** — spin off a pre-filled draft using this job's details (see below)

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
- Drag-to-reorder photos in gallery view — swipe to scroll (with a momentum glide), press &amp; hold a photo to pick it up and carry it anywhere on screen; dragging near the top/bottom edge auto-scrolls the page
- **Floating "Group selected" bar** — always reachable without scrolling
- Optional job details block (job number, client, address, date, author)
- Repositionable comment blocks (above or below photos)
- Three export options: full PDF · Photos-only PDF (for Upvise) · Single PNG image
- **PDF layout presets** — each photo/group has a layout dropdown in Detailed view: Auto (default 2-up/portrait, full-width/landscape), or a forced grid of 1, 2, 4, 6, 9, 12 or 20 per page. The denser presets (9/12/20) are photos-only — comments are skipped for legibility. For 1/2/4/6, any comments print as a numbered list under that page's photo grid.
- **Custom Layout Page Editor** — tap "Customise Page Layout" to enter a free-form canvas: drag any photo to reposition it, pinch with two fingers to resize (proportional, fit-not-crop), tap to select and use the toolbar to bring forward/send back, toggle its comment or number badge, or remove it from the page. Add/delete pages, or "Auto-arrange this page" to reset just that page to a grid. Pages here map 1:1 to PDF pages (page 1 stays the cover/header). "Reset" discards the custom layout and returns to Auto. Applies to the full PDF and Photos-only PDF — the single PNG image export still uses the Auto layout.

---

## Shared features

- 💾 **Auto-save** — drafts save automatically as you type and the moment you close or background the app, so work is never lost
- 🔍 Searchable, filterable history ("Records") — search by job number or address
- 📤 **Share editable files** — export any document as a `.json` file from Records, share to a colleague, they import it and edit on their own device
- 📥 **Import documents** — bring in a shared `.json` file via Records; choose to update your existing copy or save as a new one
- 🔁 **Promote a Day Sheet** — turn a Day Sheet straight into an Incident Report or Leak Report, with job number, address, client and PM carried over automatically
- 📞 Saved PM contacts with auto-complete; saved client list
- ➕ **Manually add** PMs, Clients, and Signatures in Settings
- 🖊️ Save signatures for re-use
- 📖 **Log Book** — every update, right in Settings
- 🌙 Light / dark / auto theme
- 📥 Backup & restore via JSON export
- 🔗 Web Share API with iOS fallback
- ✈️ Fully offline once installed

---

## Promote a Day Sheet to Incident or Leak Report

At the top of any Day Sheet (new, draft, or completed), just below **Reuse last job's details**, two gradient buttons let you spin off a related report:

- **Start Incident Report from this job** — opens a new Incident Report draft with Job Number, Site Address, Client and "Reported To" (from the Day Sheet's PM) pre-filled. Reporter name still comes from your saved settings name. Date/time are set to "now".
- **Start Leak Report from this job** — opens a new Site Report draft, type pre-set to **Leak** (still editable), with Job Number, Client and Address pre-filled. Author comes from your saved settings name.

The Day Sheet itself is **never changed** — it's saved as-is (preserving its draft/completed status), and the new report is **saved straight to Records as a draft** so the carried-over details can't be lost even if you back out immediately.

---

## Records — Sharing Editable Files

### Export (share to colleague)
1. Open **Records**
2. Tap **Select** (top-right)
3. Tick the documents you want to share
4. Tap **Export** — each document shares as its own `.json` file

### Import (receive from colleague)
1. Receive the `.json` file (AirDrop, email, Messages, etc.)
2. Open **Records**
3. Tap the **import icon** (top-right, next to Select)
4. Pick the file — it lands in Records ready to edit
5. If you already have that document: choose **Update your copy** or **Save as new copy**

> **iOS note:** On iPhone, you cannot tap a `.json` file to auto-open it in APS OnSite (iOS limitation for PWAs). Always import via the button in Records.

---

## Settings — Contacts & Signatures

PMs, Clients, and Signatures are each managed in their own sub-screen under **Settings → Contacts & Signatures**. Each shows a count and drills into a full list with add and remove.

- **Project Managers** — name + phone; auto-fills when you pick a PM on a Day Sheet
- **Clients** — name; appears in client dropdowns across all doc types
- **Saved Signatures** — enter a name, tap "Sign & Save", draw your signature; reusable across all documents

All three also auto-save whenever you complete a Day Sheet.

---

## Settings — Log Book

A read-only list of every release and what changed, newest first, with the current version badged. Updated every time `APP_VERSION` is bumped.

---

## Planned (future)

- SSSP (Site Specific Safety Plan)
- QR-code site sign-on
- Gmail / Google OAuth login
- Multi-file export bundle

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
2. Bump `CACHE_NAME` in `sw.js` (e.g. `v3.0` → `v3.1`) — this forces devices to fetch fresh files
3. Update `APP_VERSION` in `index.html` to match (shown in Settings → About)
4. Add an entry to the `CHANGELOG` array in `index.html` (shown in Settings → Log Book)
5. Wait 1–2 minutes for Pages to deploy
6. On the phone: close the app fully, reopen — new version loads automatically

**If it doesn't update:** iPhone Settings → Safari → Advanced → Website Data → find the URL → swipe to delete → reopen.

**Rollback:** Settings → Pages → switch branch to a previous stable branch.

---

## Data Protection &amp; Backups

Everything stays on the user's device (IndexedDB via localForage) — nothing is sent to any server.

iOS can, under storage pressure, clear an entire web app's data at once — records, signatures, Clients and PMs together. v4.2.1 adds layered protection:

- **Persistent storage** — requested automatically on startup. Installed (Home Screen) apps are usually granted this, which makes that kind of wipe far less likely.
- **Export All Data** (Settings → Backup &amp; Restore) — a full backup file (records, signatures, settings, Clients &amp; PMs) via the share sheet, so it can be saved to Files, iCloud Drive, or emailed to yourself. This is the only copy that survives a full device/storage wipe — export it periodically, and especially before/after picking up new Clients or PMs.
- **Import Backup** — restores a backup file. Always **merges**; nothing on the device is deleted.
- **Automatic snapshots** (Settings → Restore from Snapshot) — the app keeps the last 5 on-device snapshots, taken after finishing a report or when the app closes/backgrounds. One-tap restore (merge) if something looks wrong. These live in the same storage as everything else, so they're a convenience net, not a replacement for Export All Data.
- **Backup reminder** — a dismissible banner on the home screen if it's been over a week since the last export.
- **Storage gauge** (Settings → App) — shows how full device storage is and whether persistent storage is active.
- **Memory-safe photo uploads** — adding many photos at once (Site Report, Day Sheet, Incident Report) now processes one at a time with a progress indicator, and the save is verified afterwards. A failed/incomplete save now shows a clear warning instead of failing silently.

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
| v4.2.2 | Rebuilt gallery drag/scroll gesture — swipe scrolls (with momentum glide), press & hold lifts a photo into a free drag anywhere on screen, auto-scrolls near screen edges |
| v4.2.1 | Backups now include Clients/PMs and use the share sheet; automatic on-device snapshots with restore; backup reminder banner; storage gauge & persistent storage; memory-safe multi-photo uploads with verified saves |
| v4.2 | Custom Layout Page Editor for Site Reports (drag/pinch-resize/snap, per-photo comment & number toggles, reversible); per-item PDF layout presets (1/2/4/6/9/12/20 per page); fixed gallery scroll |
| v4.0.1 | Fixed promote buttons (removed blocking confirm, added error reporting); restyled to gradient buttons with menu icons, moved next to Reuse |
| v4.0 | Promote a Day Sheet to Incident Report or Leak Report (job details carry over, saved straight to drafts); new Log Book in Settings |
| v3.0 | Editable file export/import (Records); multi-select export; Settings sub-menus for PMs, Clients, Signatures with add/remove |
| v2.9.1 | Toolbox Talk per-member signatures; auto-save drafts |
| v2.9 | Site Report, photo editor (crop + mark up), two-finger rotate, floating group button, black-frame fix, orientation-aware PDF layout, build version in About |
| v2.x | Incident Report, history/records, theme toggle, backup/restore |
| v1.x | Day Sheet, signatures, PPE, PDF/image export |

---

Built for APS Complete Property Services · HSWA 2015 compliance
