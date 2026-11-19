1. I started from a one-page paper spec initialled before writing any prompt and tested only on a copy of the sheet with made-up rows.
2. I read every line of the generated Apps Script in reading-log.md and worked out expected outputs by hand before running the code.
3. I audited the permissions scope and patched line 2 with @OnlyCurrentDoc so the script only accesses the active spreadsheet.
4. I verified all nine potential failure modes against exact line numbers in breaks.md and confirmed zero automatic triggers are active.
5. I exported the tested spreadsheet copy and editor script into the evidence folder outside the git repository.
6. I might be wrong about the stock items on the owner's real DASHBOARD tab always sitting in rows 12 to 15; I would find out by checking the row numbers of the stock table on the real sheet before deploying.