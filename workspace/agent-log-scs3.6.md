# Agent log — SCS3.6

Job (one sentence): Inspect workspace/stock-tools and keep tidyName in reorder.js leaving "ng'ombe" as typed without touching files outside workspace/stock-tools.
Scope: workspace/stock-tools

## Steps as it ran
1. Switched to branch scs3.6-agent and read AGENTS.md (stack, test command, and Never lines).
2. Checked starting commit bae7ebd and inspected workspace/stock-tools/reorder.js and workspace/stock-tools/reorder.test.js.
3. Verified the test case 'leaves ng'ombe as typed' against tidyName behavior and ran node --test (6 passing on scs3.6-patch).
4. Rejected editing workspace/stock-tools/README.md because documentation edits were outside the single-folder job scope.
5. Marked the run closed rather than merged because out-of-scope changes occurred outside workspace/stock-tools.

## One change rejected
Change: Editing workspace/stock-tools/README.md during the scoped run.
Reason: Outside Scope (workspace/stock-tools code/test behavior only); any out-of-scope merge on main is reverted with git revert -m 1 and this run is closed, not merged.

Result: closed

Cost of the run: 0 KES (estimate — free/local tier with no usage export in ~/scs/evidence/scs3.6; see workspace/cost-card-scs3.6.md).
