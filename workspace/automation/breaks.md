# The nine breaks -- SCS3.5

| # | Break | Cannot happen because ... (line) | Found -- patched at (line, commit) |
|---|---|---|---|
| 1 | The header row counted | Cannot happen because line 7 reads `A12:C15`, skipping row 1 headers | |
| 2 | The wrong tab | Cannot happen because line 6 selects `getSheetByName("DASHBOARD")` and line 10 selects `getSheetByName("REMINDERS")` | |
| 3 | The number read as text | Cannot happen because line 9 checks exact string equality `row[2]=== "REORDER"` rather than numeric comparison | |
| 4 | The boundary | Cannot happen because line 7 explicitly bounds the read range to `A12:C15` | |
| 5 | The overwrite | Cannot happen because line 14 calls `reminders.clearContents()` before line 15 and line 16 write headers and filtered rows | |
| 6 | The invented piece | Cannot happen because `Test 1` and `Test 2` executed `checkstock()` starting at line 4, the only function in the script | |
| 7 | The silent assumption | Cannot happen because line 11 checks `if (!reminders)` and creates the sheet if missing | Found -- patched at (line 2, <HASH>) to add `/** @OnlyCurrentDoc */` |
| 8 | The trigger that runs too often | Cannot happen because Triggers tab in Apps Script has 0 automatic triggers configured (`checkstock` runs manually only) | |
| 9 | The confident wrong answer | Caught by `Edge case` in `test-log.md` (missing `REMINDERS` tab and overly broad spreadsheet permission scope) | Found -- patched at (line 2, <HASH>) |