# Sharing and retention policy -- the practice business (2026-11-18)

One page an owner can read.  The practice business is invented: no real name, address, phone or password
goes in the ask or on this page.  The client's version lives in the client folder, never in this repo.
When the page is corrected, label it on the line below.
AI-assisted, directed by me

## 1. Where files live
All active business records live in the company Shared Drive owned by the organization, not in individual staff My Drive folders. Personal My Drive is restricted to temporary drafts before moving files into the Shared Drive.

## 2. Sharing outside the business
External sharing outside the domain is blocked by default for staff in the practice OU, and newly created files default to restricted access rather than public links. Only designated managers on the Shared Drive may share approved folders externally, and external users receive viewer or commenter access unless editor access is approved.

## 3. Who can sign in
Only active staff accounts placed in the practice Organizational Unit may sign in to company Workspace services. 2-Step Verification is enforced for every user in the OU (with offline paper backup codes stored securely), and mobile devices require a screen lock and admin approval before syncing company data.

## 4. What we keep, how long, where
Active operational records stay in the company Shared Drive; financial and tax records are kept for 7 years (exact statutory period to be checked with the accountant), and routine staff drafts are purged after 1 year (to be checked). Because this Workspace edition does not include Google Vault, retention relies on Shared Drive permissions, manual archiving, and scheduled exports rather than automated Vault hold rules.

## 5. The monthly export
On the first Monday of each month, the designated admin or manager runs a Google Takeout export of key business folders and stores the dated archive in a restricted offline/local backup folder (`backups/`). Each quarter, one file is restored from the export to verify readability and record what metadata or sharing links do not carry over.

## 6. Who holds admin
Only the business owner holds the Super Admin account, protected by 2-Step Verification and offline paper backup codes, and signs in with that account only when making administrative changes. Day-to-day password resets are delegated via a scoped role when needed, and no shared admin logins are permitted.

## 7. When someone leaves
Before a leaver's final sign-off, an admin transfers ownership of their My Drive files to their manager, exports any required archive data, and immediately suspends the user account in Directory > Users. Suspended accounts are verified as blocked from signing in and are kept suspended for 30 days (to be checked) before permanent deletion.

## Receipt

- What I gave the tool (never a real name, address, phone or password): A generic prompt describing a small practice business using Google Workspace with one practice OU, a Shared Drive, 2-Step Verification, and monthly Takeout exports, using only placeholder role names.
- The ask, one job: Draft a plain-English one-page sharing, security, backup, and offboarding policy for a small practice business owner.
- A setting it named that this edition does not have: The AI draft referenced Google Vault automated retention rules and Context-Aware Access policies; struck both because our Workspace edition in the Admin console does not include Vault or Context-Aware Access.
- A number it invented, and what I replaced it with: The AI invented a 5-year tax retention period and a 90-day suspended-account grace period; replaced with 7 years (to be checked) and 30 days (to be checked) until confirmed with the owner and accountant.
- What else I changed, and why: Rewrote generic "Admin portal" paths to match the actual console paths (Directory > Users, Apps > Google Workspace > Drive and Docs > Sharing settings) and clarified that Takeout exports do not preserve live sharing permissions or native Google file ownership.
