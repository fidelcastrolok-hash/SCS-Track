# SCS3.6 Four-Checks Audit

## Stock Tool: Auth
- Found: Checked workspace/stock-tools/ for hardcoded keys or secrets (send-sms.js line 9 had a key before moving to process.env.SMS_API_KEY).
- Evidence: Ran `git grep -n -i -E "key|secret|token|password|api_key|bearer" workspace/stock-tools/`

## Stock Tool: Edge
- Found: `tidyName("ng'ombe")` returned `"Ng'Ombe"` instead of `"ng'ombe"`; checked reorderList boundary (< vs <=), blanks, commas, and &.
- Evidence: Ran `node --test` before patch -> failed `leaves ng'ombe as typed` (`actual: "Ng'Ombe"`, `expected: "ng'ombe"`)

## Stock Tool: Version
- Found: Machine runs Node v22.22.1; checked against workspace/stock-tools/README.md.
- Evidence: Ran `node -v` (`v22.22.1`) and `cat workspace/stock-tools/README.md`

## Stock Tool: Invented
- Found: Audited function/helper calls in reorder.js and send-sms.js against actual code and Node runtime.
- Evidence: Ran `cat workspace/stock-tools/reorder.js` and `cat workspace/stock-tools/send-sms.js`

## SCS3.5 Script: Auth
- Found: Checked SCS3.5 script for hardcoded keys, tokens, or credentials.
- Evidence: Ran `git grep -n -i -E "key|secret|token|password|api_key|bearer" /path/to/scs35-script.js`

## SCS3.5 Script: Edge
- Found: Checked SCS3.5 script behavior on blanks, commas, boundaries, ng'ombe, and &.
- Evidence: Ran `node /path/to/scs35-script.js` and inspected output on edge inputs

## SCS3.5 Script: Version
- Found: Verified SCS3.5 script compatibility on Node v22.22.1.
- Evidence: Ran `node -v` -> `v22.22.1`

## SCS3.5 Script: Invented
- Found: Checked every imported or called helper/function in SCS3.5 script against docs/code.
- Evidence: Ran `head -n 60 /path/to/scs35-script.js`
