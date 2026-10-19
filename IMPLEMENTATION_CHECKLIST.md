# Desktop → Android Behavior Mapping & Checklist

## Core
| Item | Status |
|------|--------|
| Data model + desktop JSON compatibility | ✅ |
| Jalali conversion / season / Thursday | ✅ |
| Dashboard, Register, Editor, Gantt, Settings | ✅ |
| Schedule optimizer (deterministic) | ✅ |
| Excel (GANTCH7, MONTHLY, GT, ST, DATA) | ✅ |
| Engineering PDF | ✅ |

## Build & delivery
| Item | Status |
|------|--------|
| Gradle Wrapper 8.9 | ✅ |
| Unit tests (Jalali, Optimizer, Excel) | ✅ sources |
| GitHub Actions → real APK artifact | ✅ workflow ready |
| Local APK in this sandbox | ⬜ needs Android SDK |
| Gantt drag-resize on mobile | ⬜ optional polish |

## How to get the APK
1. Push repo to GitHub
2. Actions → Android Build → successful run
3. Artifacts → `fars-maintenance-planner-debug-apk`
