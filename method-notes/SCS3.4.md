1. Choosing Google Sheets over a full business application fits a single-owner kiosk with tens of daily entries and no external till or bank integrations.
2. Enforcing Kenya/UK day-first locale before typing dates prevented month-day swaps from corrupting monthly sales windows.
3. Whole-column data validation on Reject the input stopped misspelled items, negative quantities, and invalid dates before they entered the ledger.
4. Restricting the Dashboard and calculated Amount column to Only you while leaving entry columns open lets the owner record daily sales without breaking formulas.
5. Hand-checking formulas against filtered rows and an out-of-month test row proved the EOMONTH date boundaries excluded prior-month activity.
6. What I might be wrong about, and how I would find out: I assumed the owner will always enter a correcting row instead of clearing unlocked entry cells when a mistake happens, and I will find out by checking File -> Version history and reviewing the ledger with the owner after their first week of live entries.
