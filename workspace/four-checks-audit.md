# SCS3.6 Four-Checks Audit

## Piece 1: Stock Tool (workspace/stock-tools/)

- Auth
  - Found: Inspected send-sms.js and ran git grep for credential patterns.
  - Evidence: git grep -n -i -E "key|secret|token|password|api_key|bearer" workspace/stock-tools/
- Edge
  - Found: tidyName("ng'ombe") returns "Ng'Ombe" instead of "ng'ombe"; check reorderList boundary (< vs <=), blanks, commas, and &.
  - Evidence: node --test -> failing test on ng'ombe before patch
- Version
  - Found: Node v22.22.1 installed; compared with workspace/stock-tools/README.md.
  - Evidence: node -v && cat workspace/stock-tools/README.md
- Invented
  - Found: Checked every function/helper used in workspace/stock-tools/ against code and docs.
  - Evidence: cat workspace/stock-tools/reorder.js && cat workspace/stock-tools/send-sms.js

## Piece 2: Own SCS3.5 Script

- Auth
  - Found: Checked SCS3.5 script for hardcoded keys, tokens, or secrets.
  - Evidence: git grep -n -i -E "key|secret|token|password|api_key|bearer" /path/to/your/scs3.5-script.js
- Edge
  - Found: Checked SCS3.5 script on blanks, commas, boundaries, ng'ombe, and &.
  - Evidence: node /path/to/your/scs3.5-script.js
- Version
  - Found: Checked SCS3.5 script compatibility against Node v22.22.1.
  - Evidence: node -v
- Invented
  - Found: Checked every imported or called helper/API in the SCS3.5 script.
  - Evidence: head -n 60 /path/to/your/scs3.5-script.js
