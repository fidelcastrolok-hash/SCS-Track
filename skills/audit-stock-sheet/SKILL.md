# audit-stock-sheet

## When to use
Use weekly when auditing a shop inventory export or AI-generated stock script before trusting reorder output.

## Steps
1. Run the script on sample stock data and count reorder items by hand.
2. Check edge cases (blanks, commas, boundaries, `ng'ombe`, `&`) and Node runtime version.
3. Check for hardcoded secrets or invented functions/APIs.
4. Record findings and evidence on the audit card.

## How you know it worked
The script output matches the hand count and all four checks have recorded findings and evidence.

Ran: 2026-11-24 — PASS (audited workspace/stock-tools and verified tests/diff).
