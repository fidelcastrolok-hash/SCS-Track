# Patch card — SCS3.6

**The bug:** tidyName("ng'ombe") in workspace/stock-tools/reorder.js turns "ng'ombe" into "Ng'Ombe" instead of leaving "ng'ombe" as typed.

**Which check:** edge

**The spec:** Leave "ng'ombe" as typed while other lower-case names still tidy as before.

**The test that shows:** leaves ng'ombe as typed (fails on bae7ebd with actual "Ng'Ombe", passes on scs3.6-patch)

**The prompt:** Patch only tidyName in workspace/stock-tools/reorder.js so "ng'ombe" is left as typed while existing lower-case names still tidy.

**Tests after the patch:** 6 ok (node --test passes all 6 tests on scs3.6-patch)

**Label:** AI-assisted, directed by me

**Tool and tier:** Browser AI assistant / Ubuntu terminal (free tier)

**Tests or checks:** node --test on scs3.6-patch (6 passing) and git diff bae7ebd..scs3.6-patch -- workspace/stock-tools

**Rights line:** not checked

**Cost:** 0

**the diff, read whole:**

| File / hunk | Change | Spec or BEYOND |
|---|---|---|
| reorder.js (+3 lines in tidyName) | Early return when name === "ng'ombe" | Spec |
| reorder.test.js (+4 lines) | Added test "leaves ng'ombe as typed" | Spec |

```diff
diff --git a/workspace/stock-tools/reorder.js b/workspace/stock-tools/reorder.js
index 056d0f5..6db9652 100644
--- a/workspace/stock-tools/reorder.js
+++ b/workspace/stock-tools/reorder.js
@@ -31,6 +31,9 @@ function groupBySupplier(list) {

 // The counter staff type item names in lower case on the phone -- tidy them for the message.
 function tidyName(name) {
+  if (name === "ng'ombe") {
+    return name;
+  }
   if (name === name.toLowerCase()) {
     return name.replace(/\b\w/g, (c) => c.toUpperCase());
   }
diff --git a/workspace/stock-tools/reorder.test.js b/workspace/stock-tools/reorder.test.js
index ea27642..70ea87d 100644
--- a/workspace/stock-tools/reorder.test.js
+++ b/workspace/stock-tools/reorder.test.js
@@ -34,3 +34,6 @@ test("formats the message", () => {
   assert.match(msg, /Building wholesaler:/);
   assert.match(msg, /Cement 50 kg: 5 left/);
 });
+test("leaves ng'ombe as typed", () => {
+assert.strictEqual(tidyName("ng'ombe"), "ng'ombe");
+});

eof

