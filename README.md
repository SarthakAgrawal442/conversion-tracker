# Conversion Tracker

A lightweight, free Progressive Web App (PWA) for counting repair-to-purchase conversions during work shifts. Designed for iPhone and iPad with a clean, clean, minimalist interface. No App Store installation, account, or backend required.

**Open the app:** https://sarthakagrawal442.github.io/conversion-tracker/

## Features

- **One-tap tracking:** Tap **+ Add conversion** to save one conversion.
- **Previous-day entry:** Use the **‹ / ›** arrows beside the date to move between days, record missed conversions, or undo a conversion on the selected day. The forward arrow stops at today; future dates cannot be selected.
- **Undo:** Remove the latest recorded conversion for the selected day.
- **Statistics:** View today/selected-day counts, this week's and this month's totals, and the current month's average per active day.
- **History:** Browse daily totals by week or month using the separate History controls.
- **Light / Dark Mode:** Switch themes with the header toggle. On first use, the app follows the device's appearance; a manual choice is remembered.
- **Offline functionality:** After initial loading, cached app files allow offline access; conversion records are kept on the device.
- **JSON backup and restore:** Save a copy of your individual conversion records and later import them without duplicating existing record IDs.
- **CSV export:** Export daily totals to Numbers, Excel, or another spreadsheet app.
- **Device-local privacy:** Teammates who install the same link each keep independent local records.

## Install on iPhone or iPad

1. Open the [live site](https://sarthakagrawal442.github.io/conversion-tracker/) in **Safari**.
2. Tap **Share → Add to Home Screen**.
3. Open **Conversion Tracker** from the Home Screen.

For offline use, open the app while connected to the internet at least once so the service worker can cache the necessary files.

## How to use

1. On the main counter, tap **+ Add conversion** whenever a repair customer purchases a product.
2. If you missed a conversion yesterday, tap the **left arrow** beside the date, then tap **+ Add conversion**. Each tap is saved under the selected date.
3. Use the **right arrow** to return toward today. You cannot advance into a future date.
4. Tap **Undo last conversion** to remove the most recently entered record for the selected date.
5. Explore weekly or monthly totals in **History**. Those arrows change the history period, not the date selected in the main counter.
6. Use the theme toggle in the header to switch between light and dark appearances.

**Note:** Entries are grouped by local **calendar date**, not by explicitly starting or ending a shift. Weeks run Monday through Sunday; months follow the calendar.

## Data, backups, and privacy

Conversion records are saved directly in the device's **IndexedDB** database. The interface's light/dark preference is stored separately in localStorage. Refreshing the page or reopening the app normally retains these records.

There are **no accounts, remote databases, analytics services, or customer-information fields**. Records are not automatically synced between iPhone and iPad, even when signed into the same Apple ID. Each installation may have its own storage.

### Back up your records

1. Select **Backup data** in the **Your data** section.
2. Save the downloaded `.json` file somewhere safe, such as **Files → iCloud Drive**.
3. If your local data is lost, reopen/reinstall the app, choose **Restore backup**, and select the JSON file.
4. The app imports saved entries and recalculates totals; entries with IDs already present are skipped.

**Backups are manual.** Any conversions recorded after your most recent backup may not be recoverable if local storage is lost. Deleting the Home Screen app, clearing website data, or browser storage eviction can remove saved records. For regular use, save a JSON backup periodically.

**Export CSV** is intended for reporting totals by date, not for restoring the full record history. JSON backup files are not encrypted by the app; keep them private.

Because GitHub Pages uses an origin shared by projects on the same `*.github.io` account domain, other scripts on that same origin could potentially access browser storage. Avoid recording sensitive customer information; none is needed for this app.

## Hosting and deployment

The static site is hosted by GitHub Pages. This repository uses **Settings → Pages → Deploy from a branch → `main` → `/ (root)`**.

New commits to `main` are deployed automatically by GitHub Pages. If an installed Home Screen app shows an older version, open the live site in Safari, refresh, and reopen the app. The service worker caches assets for offline use and checks for updated versions.

## Project files

| File | Purpose |
| --- | --- |
| `index.html` | User interface, styles, theme switching, IndexedDB records, statistics, date navigation, exports and imports |
| `service-worker.js` | Offline cache and update handling |
| `manifest.webmanifest` | PWA installation metadata |
| `icon.svg` | App icon |

## Current limitations

- No Apple Watch app or watch-to-iPhone synchronization.
- No automatic cross-device synchronization, user accounts, or shared team dashboard.
- No automatic cloud backups.
- No separate shift start/end controls; the app tracks calendar dates.

Conversion Tracker is a personal productivity tool. Before using counts for official workplace reporting, follow your organization's policies and never enter customer details.

## Disclaimer

Conversion Tracker is an independent, personal project developed for personal use and learning purposes only. It is not intended for commercial use or monetization.

This project is not affiliated with, endorsed by, or sponsored by Apple Inc. or any other organization.
