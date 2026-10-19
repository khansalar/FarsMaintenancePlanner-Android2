# Changelog

## [1.0.0-alpha04] — 2026-10-19 (Stage 4)

### Added
- Gradle Wrapper 8.9 (`gradlew`, `gradlew.bat`, `gradle-wrapper.jar`)
- Production-ready GitHub Actions workflow:
  - unit tests + assembleDebug
  - uploads real APK artifact `fars-maintenance-planner-debug-apk`
  - fails if APK is missing
- `.gitignore` for Android/Gradle
- `BUILD_REPORT.md` and `TEST_REPORT.md`

### Notes
- Local full Android build requires Android SDK (Android Studio or CI).
- Wrapper was verified: `gradlew --version` → Gradle 8.9.

## [1.0.0-alpha03] — 2026-10-19 (Stage 3)
- Excel + Engineering PDF export

## [1.0.0-alpha02] — 2026-10-19 (Stage 2)
- Activity Editor + Schedule Optimizer

## [1.0.0-alpha01] — 2026-10-19 (Stage 1)
- Project foundation
