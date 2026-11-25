# Nova — Android wrapper (WebView APK in ~15 minutes)

This folder is a complete Android Studio project. It builds an installable
**Nova.apk** that opens your live generator
(`https://perchance.org/ch4c5iwrt8`) full-screen, with microphone +
keep-screen-on. Web edits need **no rebuild** — the app always loads the
live page.

## What this APK gives you
- ✅ Installable app icon (Nova on home screen)
- ✅ Mic for voice input (permission asked on first run)
- ✅ Screen stays awake while open
- ✅ TTS voice replies work like in the browser

## What it does NOT give (honest limits)
- ❌ Running when the app is closed / phone locked
- ❌ Floating button over other apps, lock-screen widgets
- Those need native code: a foreground service + `SYSTEM_ALERT_WINDOW`
  overlay (both permissions are already declared in the manifest for a
  future update) — an Android developer job, not a wrapper job.

## Build steps (free, ~15 min, one time)
1. Install **Android Studio** (developer.android.com/studio) on a PC.
2. Copy this `nova-apk` folder to the PC. Open it via
   **File → Open** (select the folder). Let it sync — Studio downloads
   Gradle automatically on first open.
3. Connect your phone with **USB debugging ON**
   (Settings → Developer options), or use **Build → Build APK(s)**.
4. **Run ▶** installs Nova on the phone. The file is also saved at
   `app/build/outputs/apk/debug/app-debug.apk` — copy it to any phone
   to install (allow "install unknown apps" once).
5. If you rename/move the generator later, edit ONLY
   `app/src/main/res/values/strings.xml` (`app_url`) and rebuild
   (or just reinstall — 2 minutes).

## Notes
- First launch asks for **microphone** permission — allow it for 🎤.
- Keep the generator **published/saved** so the URL always loads.
- Package name: `com.nova.assistant` (change `applicationId` in
  `app/build.gradle` if you publish to Play Store).
