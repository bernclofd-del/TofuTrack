# TofuTrack

SoyTrack — Raw Material Inventory

A simple, real-time inventory tracker for soy food production. Built as a single HTML file powered by Firebase, accessible on any phone or computer browser without installing anything.

 Features
- Real-time sync: Updates on mobile show instantly on desktop and vice versa.
- Low stock alerts: Automatic visual flags for items below their reorder point.
- Transaction tracking: Logs incoming supplies (supplier, cost) and outgoing usage (batch reference).
- PIN security: 4-digit PIN lock screen with auto-lockout after 5 failed attempts.
- Mobile-first: Large buttons, simple forms, works perfectly on production floor phones.

 Tech Stack
- Frontend: Single `soytrack.html` file (Tailwind CSS, vanilla JS)
- Backend: Firebase Realtime Database (Free Spark Plan)
- Hosting: GitHub Pages (Free)

 Daily Usage (Staff)
1. Open the link in Chrome/Safari (bookmark it for easy daily access).
2. Enter the 4-digit PIN.
3. Set your name (only required once per device).
4. Receive Stock: Tap item → "Receive Stock" → fill details → Confirm.
5. Record Usage: Tap item → "Record Usage" → fill details → Confirm.
6. Check Levels: Use the "Low" or "Critical" filter buttons at the top.

 Security
- The PIN is stored as a SHA-256 hash in Firebase (never plain text).
- A session lasts 8 hours per browser before requiring the PIN again.
- 5 wrong PIN attempts lock the screen for 15 minutes.
- Change or remove the PIN via the shield icon (🔒) in the top header.

Troubleshooting
- Lost PIN: Go to Firebase Console → Realtime Database → Delete the `_settings/pin` key. The next person to open the app will be prompted to create a new one.
- Updates not syncing: Check the green "Live" dot in the top header. If red, check your internet connection.
- Export data: Click the download icon (↓) in the header to save a CSV spreadsheet of current stock levels.
```
