# Audit Stock Sheet

## When to use
Weekly before sending out stock reorder messages.

## Steps
1. Run git status and check for secrets or keys.
2. Check rows for blanks, commas, boundaries, ng'ombe, and &.
3. Run node --test and check all tests pass.
4. Record any new bug before editing code.

## How you know it worked
node --test exits with 0 failures and no secret matches remain.

Ran: 2026-11-24 — node --test ran on scs3.6-patch with 6/6 tests passing.
