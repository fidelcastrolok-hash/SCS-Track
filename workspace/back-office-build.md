# Back Office Build Notes — A Kiosk

## Overkill Verdict
Verdict: Sheets. Pattern: Inventory. Because: One owner enters tens of daily sales and restocks into a simple ledger, and the dashboard tracks current stock and reorder flags without needing a multi-user database or external integrations.

## Validation and Protection
- **LISTS tab:** Contains item names, prices, and reorder levels with no dropdown rules so new items can be added freely.
- **RECORDS tab validation (Reject the input):**
  - `DATE`: Must be a valid date (Kenya/UK locale, day-first).
  - `ITEM`: Dropdown from range `LISTS!A2:A`.
  - `DIRECTION`: Dropdown list (`IN`, `OUT`).
  - `QUANTITY`: Number greater than `0`.
  - `PRICE`: Number greater than `0`.
- **Protection (`Only you`):**
  - The entire `DASHBOARD` sheet is restricted to the builder so formulas and flags cannot be overwritten.
  - The calculated `AMOUNT` column (`RECORDS!F2:F1000`) is restricted to the builder while entry columns `A:E` remain open for daily owner entries.

## AI Receipts

| What I gave the tool | The ask, one formula | The formula it suggested, read back part by part | What I changed, and why | The hand check |
| :--- | :--- | :--- | :--- | :--- |
| Tab `RECORDS` has headings: `DATE`, `ITEM`, `DIRECTION`, `QUANTITY`, `PRICE`, `AMOUNT` (headings only, no client data). | Add `AMOUNT` for `OUT` rows dated in the current month. | `=SUMIFS(RECORDS!F:F, RECORDS!C:C, "OUT", RECORDS!A:A, ">="&(EOMONTH(TODAY(),-1)+1), RECORDS!A:A, "<="&EOMONTH(TODAY(),0))` — sums `AMOUNT` where `DIRECTION` is `OUT` and `DATE` falls between the first day (`EOMONTH(TODAY(),-1)+1`) and last day (`EOMONTH(TODAY(),0)`) of the current month. | Verified `+1` was included on the start date so the last day of the previous month is excluded. | Log row 1 (Sales This Month) |
| Tab `RECORDS` has headings: `DATE`, `ITEM`, `DIRECTION`, `QUANTITY`, `PRICE`, `AMOUNT` (headings only, no client data). | Calculate current stock for each item by subtracting `OUT` quantities from `IN` quantities. | `=SUMIFS(RECORDS!D:D, RECORDS!B:B, A10, RECORDS!C:C, "IN")-SUMIFS(RECORDS!D:D, RECORDS!B:B, A10, RECORDS!C:C, "OUT")` — sums `QUANTITY` for `IN` matching the item in `A10` minus `QUANTITY` for `OUT` matching the item in `A10`. | None; hand-made pattern matched sheet layout. | Log row 4 (Stock Now) |
| Tab `DASHBOARD` has columns `ITEM`, `STOCKNOW`, and `LISTS` has `REORDER AT`. | Flag items that need reordering when stock is at or below the reorder level. | `=IF(B10<=INDEX(LISTS!C:C, MATCH(A10, LISTS!A:A, 0)), "REORDER", "OK")` — compares current stock in `B10` against the item's reorder level in `LISTS` and outputs `REORDER` or `OK`. | None; verified conditional formatting highlights `REORDER` in red. | Log row 4 (Reorder Flag) |

## Break the Books (The Owner's Minute)
Tested from my partner's own Google account and laptop after sharing the sheet as Editor:

| What was tried | I predicted | What happened | Held? |
| :--- | :--- | :--- | :--- |
| Type a number over a formula on `DASHBOARD` | Refused by sheet protection | Google Sheets blocked the edit with a protected sheet message | Yes — Held |
| Delete a formula in `RECORDS` column `F` (`AMOUNT`) | Refused by range protection | Google Sheets blocked the edit on `F2:F1000` | Yes — Held |
| Type an item name not on `LISTS` or `0` in `QUANTITY` | Refused by data validation | Validation popup rejected the invalid input | Yes — Held |
| Type text (`abc`) in `DATE` | Refused by date validation | Validation popup rejected the non-date value | Yes — Held |
| Enter a future date (next year) | Accepted because it is a valid date | Accepted by the sheet; noted for hand check / ledger habit | Expected (rule checks valid date) |
| Leave `AMOUNT` blank on a new row | Accepted because `F` is formula-driven | Entry columns accepted; formula evaluates when quantity and price are filled | Expected |
| Clear entry cells (`A:E`) on an existing row | Accepted because entry columns are unlocked | Entry cells cleared while `F` remained locked; restored via File → Version history | Expected (recovered via Version history) |
