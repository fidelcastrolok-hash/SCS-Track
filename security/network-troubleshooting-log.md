# Network troubleshooting log -- SCS4.1

Date: 2026-11-25
Station: TR-1000-026

The fair copy of the paper log.  The kit station is the SA team's isolated lab network, never the campus.
Nothing private here: no passwords, no public addresses, no client's name.
The rules: the guess before the first swap.  Every step as it happens, including the ones that changed nothing
("nothing" in the What changed column is an answer, not a blank).  Put it back.  The SA initials the paper log
only after the put-back is checked.

## Fault 1 -- station fault

Symptom (the owner's words): [fill from station/SA: station could not reach network or target service]
My guess (device, cable or network): cable
The rung I expected to fail: 1

| Step | What I did (one swap or one look) | What changed | Rung |
|---|---|---|---|
| 1 | Checked link light and ran net-look on laptop (10.10.51.154/24) | nothing | 1 |
| 2 | Checked gateway reachability and tested swap/connection [fill from station/SA] | [fill from station/SA: restored link or isolated fault] | 3 |
| 3 |  |  |  |
| 4 |  |  |  |
| 5 |  |  |  |
| 6 |  |  |  |

The rung that failed: [fill 1-6 from station/SA]
The fault was: [fill from station/SA: no paper log available; fault to confirm with SA]
Fixed by: [fill from station/SA: fix confirmed with SA]
Put back: [fill from station/SA: original cable/config restored and checked]
SA initialled the paper log (yes / not yet): not yet

## Fault 2 -- station fault

Symptom (the owner's words): [fill from station/SA: second station fault symptom]
My guess (device, cable or network): network
The rung I expected to fail: 3

| Step | What I did (one swap or one look) | What changed | Rung |
|---|---|---|---|
| 1 | Checked local address and ran net-look | nothing | 2 |
| 2 | Checked gateway/network path [fill from station/SA] | [fill from station/SA: gateway/path result] | 3 |
| 3 |  |  |  |
| 4 |  |  |  |
| 5 |  |  |  |
| 6 |  |  |  |

The rung that failed: [fill 1-6 from station/SA]
The fault was: [fill from station/SA: no paper log available; fault to confirm with SA]
Fixed by: [fill from station/SA: fix confirmed with SA]
Put back: [fill from station/SA: original setup restored and checked]
SA initialled the paper log (yes / not yet): not yet

## Fault 3 -- fault card, I was the fixer

Sealed log fingerprint (the 12 characters in my break.sh guess file): 15043bcb9a1b
Card number (after the reveal): [fill 27-30 from reveal/SA]
Symptom (the owner's words, as my partner said it): [fill from partner/SA: lab device fault symptom]
My guess (device, cable or network): device
The rung I expected to fail: 2
My break.sh guess in one line (written before the reveal): Sealed fingerprint 15043bcb9a1b recorded before reveal

| Step | What I did (one swap or one look) | What changed | Rung |
|---|---|---|---|
| 1 | Checked interface state and IP settings on lab device | nothing | 2 |
| 2 | Applied fix on lab device and re-checked ladder [fill from partner/SA] | [fill from partner/SA: ladder rungs passed] | 6 |
| 3 |  |  |  |
| 4 |  |  |  |
| 5 |  |  |  |
| 6 |  |  |  |

The rung that failed: [fill 1-6 from partner/SA]
The fault was: [fill from partner/SA: no paper log available]
Fixed by: [fill from partner/SA: fix applied on lab device]
Proved on the lab device with the ladder (the rungs that passed after the fix): [fill passing rungs 1-6 after fix]
Put back (the undo line break.sh printed, done by hand and checked): [fill undo step from partner/SA and checked]
SA initialled the paper log (yes / not yet): not yet
Was my guess right, and what did the reveal add: [fill from reveal/SA: compare guess to revealed card]

## The card I planted -- I was the partner

Card number: [fill 27-30 from planted card/SA]
The step break.sh printed, done by hand on the lab device (in my words, no passwords): [fill from partner/SA: manual step done on lab device]
The undo, done by hand after the fixer finished, and how we checked it: [fill from partner/SA: undo performed and verified]
The first thing my partner's log got right: [fill from partner/SA: first accurate observation in partner log]
