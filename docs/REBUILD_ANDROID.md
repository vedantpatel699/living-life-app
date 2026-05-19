# Rebuild Android APK — v3.2 (tracker-only)

The PWA at https://vedantpatel699.github.io/living-life-app/app/ is already on v3.2 — exercise prescriptions stripped, energy dashboard + shift-work supplements, lipoma/sleep/photo tracking only. You only need to rebuild the APK if you want the changes installed locally on your phone.

The `www/` folder and `android/app/src/main/assets/public/` folder have already been updated with the new `index.html` (I did that for you).

## Option A — Quick rebuild (no cap sync needed)

Since the index.html is already in place, you can go straight to gradle:

```powershell
# In PowerShell, from project root
cd "C:\Users\vedan\OneDrive\Desktop\Living Life\android-build\android"
./gradlew assembleDebug
```

The APK lands at:
```
android-build\android\app\build\outputs\apk\debug\app-debug.apk
```

Copy it to your phone (USB, Drive, email) and install. You'll need to enable "Install from unknown sources" once.

## Option B — Full rebuild via Capacitor (if Option A has issues)

```powershell
cd "C:\Users\vedan\OneDrive\Desktop\Living Life\android-build"
npx cap sync android
cd android
./gradlew clean
./gradlew assembleDebug
```

## Option C — Open in Android Studio

```powershell
cd "C:\Users\vedan\OneDrive\Desktop\Living Life\android-build"
npx cap open android
```

Then in Android Studio: **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
Same APK output location as Option A.

## Verifying after install

After flashing the new APK, open the app and check:
- Today screen shows the **energy dashboard** (calories in/out, not a routine card)
- No "Begin Routine A/B/C" buttons anywhere
- No C25K timer screen
- Supplements screen header reads "🌙 Shift day schedule" on shift days, "☀ Off day schedule" otherwise
- Coach chat (if you set the Claude key) references shift/off day in its replies

## If gradle fails

Common issues:
- **`JAVA_HOME` not set** — install JDK 17, set `JAVA_HOME` to its path
- **SDK not found** — set `ANDROID_HOME` to `C:\Users\vedan\AppData\Local\Android\Sdk` (or wherever your SDK lives)
- **Network errors fetching Gradle** — first-time builds download ~1 GB. Retry on a stable network.

The full troubleshooting guide is in `BUILD_ANDROID.md`.
