1. Five passing tests hid the ng'ombe capitalization bug in tidyName.
2. Real command outputs in Found and Evidence keep audits honest.
3. Committing a failing test first on scs3.6-patch proves the bug before patching.
4. Patching one function and reading the full diff prevents accidental rewrites.
5. Branching scs3.6-agent from main and logging steps as they run protects main.
6. Least careful check on my patch: edge cases across all combined inputs — a test with blanks, commas, boundaries, ng'ombe, and & together would reveal gaps.
