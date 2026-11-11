# Hydro Habit PWA

A free, offline-first water tracker. No account, analytics, backend, or paid API.

## Deploy with GitHub Pages
1. Create a GitHub repository.
2. Upload the contents of this folder (not the folder itself).
3. In Settings → Pages, select Deploy from a branch, choose `main` and `/ (root)`.
4. Open the published HTTPS URL in Safari on iPhone.
5. Tap Share → Add to Home Screen.

## iPhone night reminder (free, works when app is closed)
A static website cannot reliably schedule a notification or send an email while closed. Use iOS Shortcuts:
1. Open Shortcuts → Automation → + → Time of Day.
2. Set the time you want (for example, 9:00 PM) and choose Daily.
3. Add action: Show Notification.
4. Use: `Hydro Habit check-in: open the app and review today's total.`
5. Turn off Ask Before Running if iOS offers that option.

This reminder is a nudge to open the app; it does not read the website's private localStorage or send the water total. To automatically email the exact total, you would need a backend/email integration or a more involved iOS Shortcut workflow.

## Data and privacy
- Entries and goal are stored in browser localStorage on this device.
- Service worker caches the app shell so it can open offline after the first successful online visit.
- Clearing Safari website data can erase the local history. This version does not sync between devices.
- The weekly summary and streak are calculated from local history.

## Notes
- Haptics use `navigator.vibrate` when supported; iOS Safari generally does not expose reliable web haptics. Visual feedback is included.
- Install as a Home Screen web app for the standalone app experience.
