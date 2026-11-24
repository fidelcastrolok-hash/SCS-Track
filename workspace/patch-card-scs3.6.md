# SCS3.6 Patch Card

- The bug: `tidyName("ng'ombe")` turns `"ng'ombe"` into `"Ng'Ombe"` instead of leaving `"ng'ombe"` as typed.
- Which check: Edge cases (`ng'ombe`).
- The spec: Leave `"ng'ombe"` as typed while lower-case names without that exception still tidy as before.
- The test that shows: `leaves ng'ombe as typed` in `workspace/stock-tools/reorder.test.js` (fails before patch with `actual: "Ng'Ombe"`, `expected: "ng'ombe"`).
- The prompt: Patch only `tidyName` in `workspace/stock-tools/reorder.js` so `"ng'ombe"` stays as typed.
- Tests after the patch: `node --test` passed 6 of 6 tests (`✔ leaves ng'ombe as typed`).
- Label: AI-assisted, directed by me
- Tool and tier: AI assistant / local terminal (free tier)
- Tests or checks: `node --test` and `git diff workspace/stock-tools/reorder.js`
- Rights line: not checked
- Cost: 0

## the diff, read whole

| Diff line | Note / BEYOND check |
| :--- | :--- |
| `+  if (name === "ng'ombe") {` | Needed for the spec: matches `"ng'ombe"` before title-casing. |
| `+    return name;` | Needed for the spec: returns `"ng'ombe"` unchanged. |
| `+  }` | Needed for the spec: closes the `if` block inside `tidyName`. |
