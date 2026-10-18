# Daily Habit Tracker — Android PWA

## Files
- `index.html`: your original tracker, with PWA metadata and service-worker registration added.
- `manifest.json`: app name, install appearance, and icon declarations.
- `sw.js`: caches the app shell for offline reopening.
- `icons/`: 192px and 512px PNG app icons.

## Deploy with GitHub Pages
1. Sign in to GitHub and create a new repository (for example `daily-habit-tracker`).
2. Upload the contents of this folder to the repository root. Ensure `index.html`, `manifest.json`, and `sw.js` are at the root, with the `icons` folder alongside them.
3. Open the repository's **Settings → Pages**.
4. Under the build/deployment source, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
5. Wait for deployment, then open the HTTPS URL shown on the Pages settings screen.
6. On Android, open that URL in Chrome. Use Chrome's menu → **Install app** or **Add to Home screen** (wording may vary).
7. Open the installed app and test Today, Month, Reminders, then briefly go offline and reopen it.

## Data and reminder notes
- Habit data remains in browser `localStorage` on this device/browser profile. It is not cloud-synced.
- Avoid clearing Chrome/site storage unless you have exported or otherwise backed up your data; the original app has no export feature.
- The service worker caches the app shell, not a server or cloud database.
- Existing reminders only check the time while the app page is open. This PWA does not guarantee alarms/notifications while closed. For reliable time-based alarms, use the phone's Clock app.
- When you update files later, change `CACHE_NAME` in `sw.js` (for example to `daily-habit-tracker-v2`) to encourage clients to refresh cached assets.
