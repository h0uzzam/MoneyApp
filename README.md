# Money MAD v4

## Changes
- Paid bills now move to a separate **Paid bills** section on the Plan page. Marking paid records the paid date; Undo returns it to unpaid bills.
- Insights now has This month, This year and All time filters. Income, expenses and category spending change with the selected period. Trend chart displays monthly spending appropriate to the selection (all-time chart shows the latest 12 months while totals/categories include all history).
- Bill due reminders are checked when the app is open. If browser notification permission is granted, a local notification can appear while the page is active; otherwise an in-app notice appears.

## Push notification limitations
This version does **not** send reliable push notifications while the app is closed. A web push implementation on iOS requires the app to be added to the Home Screen, iOS/iPadOS 16.4 or later, user permission, a push subscription, and a push server/service to deliver scheduled reminders. A static GitHub Pages site cannot run the required scheduled backend by itself. A fully local scheduled notification is generally better handled by a native iOS app with notification permissions. No app should claim background bill alerts are working until that delivery infrastructure is implemented and tested.

## Install/update
Upload the five app files to your HTTPS host, replacing the old versions. If the old service worker keeps showing the prior app, close the Home Screen app, reload the site in Safari, and reopen it. If needed, remove and re-add the Home Screen shortcut after the new site has deployed.

## Data and privacy
Records remain in local browser storage; the app does not send financial data to a server. Make JSON backups regularly. The app includes manual iCloud Drive backup/restore, not automatic iCloud sync.
