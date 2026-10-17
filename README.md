# Heritage Land Survey — Mobile App

This repository is configured for:
- Android APK builds using GitHub Actions.
- PWA deployment to GitHub Pages.
- Offline use of the app shell and saved survey data where supported.

## Source files required in the repository root

Upload these files from `Heritage_Survey_PWA.zip` into the root of this repository:
- `index.html`
- `manifest.json`
- `sw.js`
- `icon-192.png`
- `icon-512.png`

The workflow only builds after `index.html`, `manifest.json`, and `sw.js` are present.

## Get the Android APK

1. Open the **Actions** tab.
2. Select **Heritage Survey Mobile Build**.
3. Open the latest successful run.
4. Under **Artifacts**, download **Heritage-Survey-Android-APK** and extract the ZIP.
5. Install `app-debug.apk` on an Android device. You may need to allow installs from your browser/file manager.

## Get the PWA

The workflow deploys the PWA to GitHub Pages. After the first successful deployment, open **Settings → Pages** to see the site URL, then open it in Chrome on Android and choose **Install app** or **Add to Home screen**.

## Offline notes

The app files and locally saved survey information can be available offline after the app has been loaded/installed. OpenStreetMap tiles are fetched online and are not cached by the current service worker, so the map background may be blank offline. GPS requires device location permission and may require internet for map imagery.

## Important

The APK workflow creates a debug APK for direct testing, not a Play Store release build. Keep a secure backup of any future release-signing key.