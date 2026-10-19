# Test Report — Fars Maintenance Planner Android

**Date:** 2026-10-19

## Unit tests present

| Class | Coverage |
|-------|----------|
| `JalaliUtilsTest` | Conversion, round-trip, season, Thursday, Persian digits |
| `ScheduleOptimizerTest` | Empty plan, Thursday starts, +7 steam rule, fixed durations, determinism, missing gas error |
| `ExcelExporterTest` | Worksheet names (GANTCH7, GANTCH_MONTHLY, GT, ST, DATA), unit presence in DATA |

## Execution status in this environment

- Gradle Wrapper: **OK**
- Full test task: **not executed** (Android SDK absent)
- CI is configured to run the full suite on every push

## Manual verification checklist (after APK install)

- [ ] Import desktop `maintenance_data.json`
- [ ] Dashboard metrics match entry counts
- [ ] Add / edit / delete activity
- [ ] Run optimizer → review notes → apply
- [ ] Export Excel and open in spreadsheet app
- [ ] Export PDF and check S1/S2/S3 labels + English digits
- [ ] Gantt shows season Aban–Khordad only
