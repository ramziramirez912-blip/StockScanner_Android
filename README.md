# Stock Scanner - Android Project & APK Guide

This directory contains the complete native Android project for **Stock Scanner**, ready to compile into a standalone `.apk` package.

---

## Project Structure

- `app/src/main/assets/`: Contains `StockScanner.html`, `html5-qrcode.min.js`, `manifest.json`, and app icons. Everything runs 100% offline.
- `app/src/main/java/com/stockscanner/app/MainActivity.java`: Native Android container featuring:
  - Fullscreen hardware-accelerated `WebView`.
  - Automatic camera permission handling (`onPermissionRequest`) for live barcode/QR code camera scanning.
  - Native file download bridge (`AndroidBridge.saveFile`) saving Excel spreadsheets and JSON backups directly to the device's `Downloads` directory.
  - Offline persistent storage (`DOMStorage` / `LocalStorage`).
- `app/src/main/res/`: Launcher icons (`mipmap-mdpi` through `mipmap-xxxhdpi`), themes, styles, and colors.
- `.github/workflows/build-apk.yml`: Automated CI/CD script to compile the APK in GitHub Actions.

---

## 3 Ways to Get and Run the APK on Android

### Method 1: Build with Android Studio (Recommended)
1. Open **Android Studio** on any computer.
2. Select **Open** and choose this `StockScanner_Android` folder.
3. Wait a few seconds for Gradle to sync.
4. In the top menu, click **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. Once built, Android Studio shows a notification with a **locate** link to:
   `app/build/outputs/apk/debug/app-debug.apk`
6. Transfer `app-debug.apk` to your Android phone via USB, Google Drive, or email, tap it, and click **Install**.

---

### Method 2: Free Automated Cloud Build via GitHub Actions
If you don't have Android Studio installed:
1. Push this folder to a GitHub repository (private or public).
2. The included `.github/workflows/build-apk.yml` workflow triggers automatically.
3. Go to the **Actions** tab in your GitHub repository.
4. Click on the latest workflow run and scroll to **Artifacts** at the bottom.
5. Download **StockScanner-Debug-APK** (it gives you the compiled `.apk` file ready to install).

---

### Method 3: Instant Installation on Android via PWA / WebAPK (No compilation required!)
Stock Scanner includes a Web App Manifest and Service Worker:
1. Host the `StockScanner` folder (e.g. via GitHub Pages, Vercel, or local Wi-Fi server) or transfer the `StockScanner` folder to your phone.
2. Open `StockScanner.html` in **Google Chrome** on your Android phone.
3. Tap the browser menu (**⋮**) in the top right.
4. Tap **"Install app"** or **"Add to Home screen"**.
5. Android will automatically package and install it as a real **WebAPK** with its own home screen icon, standalone window (no address bar), camera access, and offline data storage!
