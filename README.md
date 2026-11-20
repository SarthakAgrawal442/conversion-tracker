# Conversion Tracker

A free, installable iPhone web app for tracking conversions. One tap records one conversion. Daily, weekly and monthly totals are calculated automatically.

## Use on your iPhone

After GitHub Pages is enabled, open `https://sarthakagrawal442.github.io/conversion-tracker/` in Safari, then choose **Share → Add to Home Screen**.

## Enable hosting

In this repository go to **Settings → Pages → Build and deployment → Deploy from a branch**. Select `main` and `/ (root)`, then **Save**. GitHub will publish the site over HTTPS.

## Data storage and privacy

Each conversion is saved to local IndexedDB on that iPhone, not uploaded to a server. Refreshing or closing the app does not normally erase it. Removing the app, clearing website data, or browser storage eviction can erase local records, so periodically use **Backup data** and store the JSON file in Files/iCloud Drive. **Restore backup** supports backups from Conversion Tracker and the previous ShiftCounter prototype. **Export CSV** exports daily totals.

Each teammate opening the same URL has their own separate local history. No sign-in, shared dashboard, customer data or analytics. The counter tracks calendar days rather than manually defined shifts; totals are Monday–Sunday and calendar months.

## Source

- `index.html`: interface, styling and IndexedDB logic.
- `manifest.webmanifest` and `icon.svg`: app installation metadata.
- `service-worker.js`: offline caching.

This is a first version; test on an actual iPhone before relying on it for team-wide tracking.
