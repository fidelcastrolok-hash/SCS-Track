# Patch card — SCS3.6

The bug: tidyName("ng'ombe") in workspace/stock-tools/reorder.js turns "ng'ombe" into "Ng'Ombe" instead of leaving "ng'ombe" as typed.
Which check: edge
The spec: Leave "ng'ombe" as typed while other lower-case names still tidy as before.
The test that shows: leaves ng'ombe as typed
The prompt: Patch only tidyName in workspace/stock-tools/reorder.js so "ng'ombe" is left as typed while existing lower-case names still tidy.
Tests after the patch: 6 ok
Label: AI-assisted, directed by me
Tool and tier: Browser AI assistant / Ubuntu terminal (free tier)
Tests or checks: node --test workspace/stock-tools/reorder.test.js (6 ok) and git diff bae7ebd..scs3.6-patch -- workspace/stock-tools
Rights line: not checked
Cost: 0

the diff, read whole:

| File | Hunk / lines | Spec or BEYOND | Notes |
|---|---|---|---|
| workspace/stock-tools/reorder.js | +if (name === "ng'ombe") return name; | Spec | Keeps ng'ombe as typed |
| workspace/stock-tools/reorder.test.js | +test("leaves ng'ombe as typed", ...) | Spec | Fails before patch, passes after |
