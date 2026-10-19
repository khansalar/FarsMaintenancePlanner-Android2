# Build Report — Fars Maintenance Planner Android

**Date:** 2026-10-19  
**Version:** 1.0.0-alpha03

## Environment (this workspace)

| Item | Value |
|------|--------|
| JDK | OpenJDK 17 |
| Gradle Wrapper | 8.9 (committed) |
| Android SDK in workspace | **Not installed** (expected) |
| Full local `assembleDebug` | Blocked until SDK is present |

## What was verified here

1. **Gradle Wrapper** starts successfully (`sh gradlew --version` → Gradle 8.9).
2. Project structure is complete for Android Studio / CI.
3. Unit test sources exist for:
   - JalaliUtils
   - ScheduleOptimizer
   - ExcelExporter
4. Attempted `./gradlew test` failed only with:
   > SDK location not found  
   This is expected in a headless environment without Android SDK.  
   **GitHub Actions installs the SDK** via `android-actions/setup-android@v3` and will run tests + assembleDebug.

## How to produce a real APK

### Option A — GitHub Actions (recommended)

1. Push this repository to GitHub.
2. Open **Actions** → **Android Build**.
3. Run workflow (push or `workflow_dispatch`).
4. Download artifact: **`fars-maintenance-planner-debug-apk`**.

### Option B — Local Android Studio

1. Open `FarsMaintenancePlanner-Android` in Android Studio.
2. Let it sync Gradle and install missing SDK components.
3. Run:
   ```bash
   ./gradlew test assembleDebug
   ```
4. APK: `app/build/outputs/apk/debug/app-debug.apk`

## CI workflow

File: `.github/workflows/android-build.yml`

- Triggers: push / PR / manual
- JDK 17 + Android SDK
- `./gradlew test`
- `./gradlew assembleDebug`
- Uploads real APK artifact (fails if APK missing)

## Known build notes

- `minSdk 26`, `compileSdk 35`, Kotlin 2.0.21, Compose BOM 2024.10.01
- Apache POI and PDFBox Android are in dependencies (larger APK)
- Debug APK is unsigned (installable on devices with unknown sources)
