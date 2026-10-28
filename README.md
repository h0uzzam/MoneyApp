# Money MAD — private iPhone finance app with iCloud Drive backup workflow

## iCloud limitation (important)
An installable Safari web app/PWA cannot silently read or write to a user's private iCloud Drive. Apple does not expose a general iCloud Drive filesystem API to ordinary websites. True automatic iCloud sync typically needs a native iOS app using Apple's CloudKit/iCloud entitlements, which involves an Apple developer workflow, or a separate sync backend with user authentication. A no-subscription native route may still be possible for personal use but takes more setup and testing.

## Recommended free approach
This version keeps records locally on the iPhone and provides a manual JSON backup/restore flow. To back up:
1. Open Money MAD → Settings.
2. Tap **Back up to Files / iCloud Drive**.
3. On iPhone, if Safari downloads the file, open the download and use Share → Save to Files.
4. Save to **iCloud Drive → Money MAD Backups**. Create that folder if needed.
5. Repeat weekly and after important changes.

To restore:
1. Download/open the JSON backup from iCloud Drive and save it into Files if needed.
2. Open Money MAD → Settings → Restore backup.
3. Choose the backup JSON file and confirm replacement.

The export includes all app data and attached receipt photos. Treat it as sensitive financial information.

## Features
Income/expenses/transfers, accounts, category budgets, bills, savings goals, debts, reports, receipt photos, CSV export, JSON backup/restore, light/dark themes, local-only data.

## Install
Upload `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, and `icon-512.png` to the root of a GitHub repository. Under Settings → Pages choose deploy from `main` and `/ (root)`. Open the published HTTPS address in Safari on iPhone → Share → Add to Home Screen.

## Privacy and limitations
- App financial data is stored in browser local storage and is not sent to a server by this code.
- The app does not automatically sync between devices and cannot silently create files in iCloud Drive.
- Browser data may be erased by clearing Safari data or other storage eviction; backups are strongly recommended.
- Automatic iCloud sync would require a native iOS app using CloudKit, or a separately authenticated cloud backend. Do not add third-party scripts without reviewing their privacy implications.
- No automatic bank connection, bill payment, scheduled push notification, or recurring transaction generation.
