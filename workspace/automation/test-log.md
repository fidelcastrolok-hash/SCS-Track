# Test log -- SCS3.5

| Case | Input rows (made up) | Expected (by hand, before the run) | Actual (after the run) | Pass or fail | Patch (line, commit) |
|---|---|---|---|---|---|
| Test 1 | `DASHBOARD!A12:C13`: `["Sugar", 2, "REORDER"]`, `["Milk", 15, "OK"]` | `REMINDERS` cleared; row 1 has `ITEM, CURRENT STOCK, STATUS`; row 2 has `Sugar, 2, REORDER` | `REMINDERS` shows headers in row 1 and `Sugar, 2, REORDER` in row 2 | Pass | — |
| Test 2 | `DASHBOARD!A12:C15`: all 4 rows have `STATUS = "OK"` | `REMINDERS` cleared; row 1 has headers only; no range error when 0 rows match | `REMINDERS` shows row 1 headers only with no error | Pass | — |
| Edge case | `REMINDERS` tab deleted before running `checkstock()` + full Drive permission scope | Script previously requested all spreadsheets scope; after adding `/** @OnlyCurrentDoc */` at line 2, creates `REMINDERS` and scopes permissions to current doc only | `REMINDERS` created and populated under current-doc scope | fail -> pass | line 2, <HASH> |
| Second edge case (optional, SGL menu) | — | — | — | — | — |
| Partner as a careless owner | — | — | — | — | — |
| Re-run in front of the trainer | — | — | — | — | — |