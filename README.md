# Vivasaya Sevai Kanakku — Offline Android starter

This is an offline-first starter Android app. It loads a bundled local HTML interface inside Android WebView, so the core customer and billing screens work without an internet connection.

## Included
- Customer name and contact number
- Acres and configurable insurance rate per acre
- Printing, Xerox, and other charges
- Automatic total, paid, pending, and payment status
- Multiple partial payments per customer
- Search and status filters
- Account receipt with Print / Save as PDF through Android's print flow where supported
- Local JSON backup export and import
- Persistent local storage on the device
- GitHub Actions workflow to build a debug APK

## Important limitations
- This starter stores records locally on one device. It does **not** yet provide online accounts or sync between multiple users/devices.
- Data is stored in WebView local storage. Export backups regularly; clearing app storage or uninstalling the app may remove records.
- The included receipt print action depends on the Android WebView/browser print support available on the device. Verify on the target phone.
- This is a starter build, not a security-audited production financial system.

## Build APK using GitHub Actions from a phone
1. Create a GitHub repository named `vivasaya-sevai-kanakku`.
2. Upload all files and folders from this project to the repository (keep folder structure).
3. Commit to the `main` branch.
4. Open the repository's **Actions** tab.
5. Select **Build Offline Android APK** and tap **Run workflow** (or wait for the workflow after a push).
6. Open the completed workflow run and download the artifact named `vivasaya-sevai-kanakku-offline-apk`.
7. Extract the downloaded ZIP to get `app-debug.apk`, then install it on your Android phone. Android may ask permission to install apps from that source.

## Build locally in a configured Android/Gradle environment
Requires JDK 17, Android SDK platform 35, and compatible Android build tools:
```bash
gradle assembleDebug
```
APK output:
`app/build/outputs/apk/debug/app-debug.apk`

## Backup
Use **Export Backup** regularly and store the JSON file somewhere safe. Use **Import Backup** to restore a backup on this device.
