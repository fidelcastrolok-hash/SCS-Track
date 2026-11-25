# Method note -- SCS4.1

## 1. What I set out to do
Complete the SCS4.1 network checks, troubleshooting log, router hardening record, AI receipt, and screenshot evidence on TR-1000-026.

## 2. What I did, in order
Ran net-look on Ubuntu-SCS, checked the guess fingerprint (15043bcb9a1b), restored the SCS4.1 templates, and filled out the log, hardening record, receipt, and method note.

## 3. How I checked it worked
Ran check-scs4.1 and verified net-look output (10.10.51.154/24, gateway 10.10.51.1) and git commit status.

## 4. What went wrong and what I did about it
Overwriting starter headings initially kept checks from matching and I did not have the physical paper logs on hand, so I restored the templates and marked unverified station details for SA confirmation.

## 5. What I would do differently next time
Record all paper log entries, card numbers, and router/printer details immediately during the lab before leaving the station.

## 6. What I might be wrong about, and how I would find out
I might be wrong about which rung failed on the physical station or whether gateway 10.10.51.1 failing ping on bootcamp Wi-Fi reflects a real fault; I would find out by checking the station and router directly with the SA and re-testing the ladder.
