# AGENTS.md

## Stack
- Node.js (v22.22.1) and JavaScript (`node:test`) in `workspace/stock-tools/`.

## Tests
- `node --test workspace/stock-tools/reorder.test.js`

## Never
- Never leave API keys or secrets hardcoded in source files or git history.
- Never trust unverified or invented functions without checking official docs first.
- Never modify files outside `workspace/stock-tools/` during a scoped stock-tool task.
- Never accept AI edits without reading the full diff first.
