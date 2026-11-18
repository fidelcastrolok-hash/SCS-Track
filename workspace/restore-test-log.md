# Restore test log -- the practice business (2026-11-18)

A backup nobody has restored from is a hope.  'It worked' is not an entry: say what did not come back,
or what you checked to be sure nothing is missing.

| # | Restore | What I deleted or suspended | How I restored it | How long | What came back | What did not come back |
|---|---|---|---|---|---|---|
| 1 | The suspended user, restored whole | Suspended amina.otieno in Directory > Users | Clicked Reactivate on the suspended user profile in Admin console > Directory > Users | 2 min | Full mailbox, calendar, OU placement, and sign-in access returned intact | Active session tokens and previously transferred Drive files (front-desk-notes.docx) remained with the manager |
| 2 | A file from the shared drive's trash | Deleted staff-rota.xlsx from the practice Shared Drive | Opened Shared Drive > Trash, selected staff-rota.xlsx, and clicked Restore | 1 min | staff-rota.xlsx and its edit history returned to its original folder in the Shared Drive | Nothing was missing; verified file size, rows, and Shared Drive member permissions were unchanged |
| 3 | A user's deleted file, restored by the admin | Deleted client-intake-2026.docx from My Drive and emptied user Trash | Admin console > Directory > Users > Restore data (selected date range and Drive) | 3 min | client-intake-2026.docx reappeared in the user's My Drive root folder | Custom sharing links and original subfolder placement did not come back; verified document text was intact |
| 4 | One file from the export | Extracted front-desk-notes.docx from takeout-20261118T103000Z-001.zip | Unpacked Takeout/Drive/front-desk-notes.docx into restore-test and opened it | 2 min | Full document text and formatting came back intact as a .docx file | Live Google Doc comments, sharing permissions, and original owner metadata did not come back |
