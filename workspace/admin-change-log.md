# Admin change log -- SCS3.1

Date: 2026-11-17
Sandbox admin sign-in: fisher@<sandbox domain>
My unit: /Trainees/fisher
Naming convention: first.last

One row per admin action, written BEFORE the click.  A ticket may take several rows; add them as you go.
Logged at: the time on the laptop clock when you wrote the row.
Console path: where you expect to click, with ">" between the steps; correct it after if the console differs.
Audit log: filled in SGL/Lab -- the time the console's audit log shows for this change, or "gap:" and why.
Never write a password here.  The first password is handed over by voice.

| # | Ticket | Logged at | What I am about to change (console path) | Who or what it affects | Why (the three questions, one line) | How I checked it | Audit log |
|---|---|---|---|---|---|---|---|
| 1   | 1 New starter    | 10:50     | Admin console > Directory > Users > Add new user                              | amina.okello, new Front Desk starter                                         | The job needs counter email and calendar, extra access risks financial records, the owner decided             | Verified user appears active in users list and signed in via private window     | 10:52     |
| 2   | 2 Groups         | 10:55     | Admin console > Directory > Groups > Create group                             | counter@<sandbox-domain>, counter staff                                      | Staff need one shared address for shift rotas, wider access exposes management mail, the shop manager decided | Verified group page lists all counter members                                   | 10:57     |
| 3   | 3 Units          | 11:00     | Admin console > Directory > Organizational units > Create organizational unit | Front Desk under /Trainees/fidelcastrol/Staff                                | Chat must be turned off for counter staff only while other staff keep it, the owner decided                   | Verified Front Desk OU appears in tree and moved new starter into it            | 11:02     |
| 4   | 4 Delegated role | 11:05     | Admin console > Account > Admin roles > Assign users                          | Accountant user in /Trainees/fidelcastrol/Staff, Password Reset Admin        | The job needs password resets for staff only, full admin risks billing and data deletion, the owner decided   | Signed in as accountant and tested three actions to confirm role limits         | 11:07     |
| 5   | 5 Rollback       | 11:10     | Admin console > Account > Admin roles > Unassign users                        | Accountant user in /Trainees/fidelcastrol/Staff, remove Password Reset Admin | The role test is complete and elevated privileges are no longer needed, the trainer decided                   | Confirmed Password Reset Admin role is removed from the accountant user profile | 11:12     |


## Gaps


none


## Audit match

## SCS3.2 -- sharing, security, backups, offboarding (2026-11-18)

Practice OU only.  Every row written before the click; the check column filled after it.

| # | Time | What I am about to change (console path) | Who or what it affects | Why, in one line | How I checked it | Undo |
|---|---|---|---|---|---|---|
| 1 | 09:05 | Admin console > Apps > Google Workspace > Drive and Docs > Sharing settings > Sharing options | Practice OU external file sharing | Prevent accidental data leaks outside the practice business (logged post-click) | Partner external share attempt blocked/warned and screenshot saved | Set Sharing options back to On for practice OU |
| 2 | 09:12 | Admin console > Apps > Google Workspace > Drive and Docs > Sharing settings > Link sharing | Practice OU default file links | Prevent public link exposure on newly created Drive files (logged post-click) | Verified default link sharing restricted in Drive settings | Revert default link sharing to Anyone with the link |
| 3 | 09:18 | Admin console > Apps > Google Workspace > Drive and Docs > Sharing settings > Shared drive creation | Practice OU users | Control who can create new Shared Drives to avoid sprawl (logged post-click) | Verified Shared Drive creation policy applied to practice OU | Re-enable Shared drive creation for practice OU |
| 4 | 09:25 | Admin console > Apps > Google Workspace > Drive and Docs > Manage shared drives > Create | Practice business Shared Drive | Centralize company files so ownership remains with the business (logged post-click) | Confirmed practice Shared Drive appears in Drive and Admin console | Move files out and delete the practice Shared Drive |
| 5 | 09:32 | Admin console > Apps > Google Workspace > Drive and Docs > Manage shared drives > Settings | Practice Shared Drive members | Restrict external sharing and downloads to Content Managers/Managers (logged post-click) | Verified member permissions in Shared Drive settings | Reset Shared Drive sharing settings to default |
| 6 | 09:40 | Admin console > Security > Authentication > 2-step verification | Practice OU user accounts | Enforce 2FA to protect accounts against credential theft (logged post-click) | Verified 2-step enforcement in Users CSV export | Turn off 2-step verification enforcement for practice OU |
| 7 | 09:48 | User account > Security > 2-Step Verification > Enroll & print backup codes | Practice user account | Complete 2FA enrollment and generate offline paper recovery codes (logged post-click) | Verified 2-step screen screenshot and paper codes in pocket | Disable 2-step verification on practice user account |
| 8 | 09:56 | Admin console > Devices > Mobile and endpoints > Settings > Universal settings | Practice OU mobile endpoints | Require screen lock and basic management on synced devices (logged post-click) | Verified mobile management rule active for practice OU | Disable screen lock and device management requirement |
| 9 | 10:05 | Admin console > Devices > Mobile and endpoints > Settings > Device approvals | Practice OU devices | Block unapproved endpoints from syncing company Drive data (logged post-click) | Verified device approval setting in Devices console | Turn off admin approval requirement for devices |
| 10 | 10:15 | Admin console > Apps > Google Workspace > Drive and Docs > Transfer ownership | Leaver account to practice manager | Retain business files under manager ownership before offboarding (logged post-click) | Confirmed ownership transfer events in Drive audit log CSV | Transfer file ownership back to original user |
| 11 | 10:25 | Admin console > Directory > Users > Suspend user | Leaver user account in practice OU | Immediately revoke leaver sign-in access after file transfer (logged post-click) | Verified Suspended status in Users CSV and sign-in blocked | Click Reactivate user on the leaver account |
| 12 | 10:45 | Admin console > Directory > Users > Reactivate user | Leaver user account in practice OU (reset) | Un-suspend practice user at end of lab so the practice OU is left whole (logged post-click) | Verified Active status in final Users CSV export | Click Suspend user on the practice user account |
