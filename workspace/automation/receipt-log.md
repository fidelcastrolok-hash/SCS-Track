# AI receipt log -- SCS3.5

Label: AI-assisted, directed by fisher
Tool: Gemini
Spec initialled on (YYYY-MM-DD): 2026-11-19
First prompt sent on (YYYY-MM-DD HH:MM): 2026-11-19 09:00

## The one prompt, word for word
Write a Google Apps Script on Google Sheets with a comment on every line for a function named checkstock that reads rows 12 to 15 of columns A to C on the DASHBOARD tab (ITEM, CURRENT STOCK, STATUS), filters rows where STATUS equals REORDER, clears the REMINDERS tab (creating it if missing), writes the headers ITEM, CURRENT STOCK, STATUS in row 1, and writes the matching rows starting at row 2. Made-up rows: Sugar (2, REORDER), Milk (15, OK).

## What came back, and what I changed by hand
The tool returned the checkstock() function reading DASHBOARD!A12:C15 and writing filtered REORDER items to REMINDERS. By hand, I added `/** @OnlyCurrentDoc */` at line 2 (commit <HASH>) so Apps Script only requests permission for the current spreadsheet instead of all spreadsheets.

## Iteration -- only if the draft missed a line of the spec (which line)
None — the draft matched all lines of the spec on the first pass.

## The debug move -- one real error: the message pasted whole, what my trace said first, what the tool said
None encountered during the clean run on the copy.