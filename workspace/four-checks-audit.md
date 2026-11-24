# SCS3.6 Four-Checks Audit

## Stock Tool (workspace/stock-tools/)

### auth
Found: Removed hardcoded SMS key from send-sms.js to read process.env.SMS_API_KEY and checked git grep.
Evidence: git grep -n -i -E "key|secret|token|password|api_key|bearer" workspace/stock-tools/

### edge
Found: tidyName("ng'ombe") returned "Ng'Ombe" instead of "ng'ombe"; checked blanks, commas, boundaries, and &.
Evidence: node --test -> failed leaves ng'ombe as typed (actual: "Ng'Ombe", expected: "ng'ombe") before patch

### version
Found: Node v22.22.1 installed on machine; checked against workspace/stock-tools/README.md.
Evidence: node -v -> v22.22.1

### invented
Found: Checked functions and helpers in reorder.js and send-sms.js against actual code and Node APIs.
Evidence: cat workspace/stock-tools/reorder.js && cat workspace/stock-tools/send-sms.js

## SCS3.5 Script

### auth
Found: Checked SCS3.5 script for hardcoded keys, tokens, or secrets.
Evidence: git grep -n -i -E "key|secret|token|password|api_key|bearer" /path/to/scs35-script.js

### edge
Found: Checked SCS3.5 script on blanks, commas, boundaries, ng'ombe, and &.
Evidence: node /path/to/scs35-script.js

### version
Found: Verified SCS3.5 script runtime against Node v22.22.1.
Evidence: node -v -> v22.22.1

### invented
Found: Checked every imported or called function in SCS3.5 script against docs and code.
Evidence: head -n 60 /path/to/scs35-script.js
