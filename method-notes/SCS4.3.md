# SCS4.3 Method Notes

1. Capture baseline and inspect firewall, listeners, cron backup job, and startup services read-only.
2. Verify archive integrity (sha256 and archive test) and run isolated restore tests without touching live data.
3. Compare restored files and database records against live state, then remove temporary restore artifacts.
4. Copy evidence to the laptop and off-host stick, keeping secrets and archives out of Git.
5. Document baseline state, backup/restore results, and fault card findings clearly.
6. Re-run check-scs4.3 and confirm all automatic checks pass before committing changes.
