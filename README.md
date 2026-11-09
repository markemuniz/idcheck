# TTA ID Check

A license and state ID scanner for The Travel Agency's four stores: SoHo, Union Square, Downtown Brooklyn and 5th Ave.

Plug a 2D barcode scanner that reads PDF417 into the computer, open the page, and scan the back of the ID. The page shows CLEARED, UNDER 21, EXPIRED or CHECK ID. It reads every US state, DC, US territory and Canadian province.

## Privacy

Only age, result, reason, issuing state, store, station and time are saved. Names, birth dates, ID numbers and addresses are shown on screen, cleared after a few seconds, and never stored (9 NYCRR 123.10(d)(5)).

## Setup

1. Create a Firebase project. In Authentication, turn on **Anonymous** and **Google** sign-in, and add `markemuniz.github.io` under Authorized domains.
2. Create a Firestore database and paste `firestore.rules` into its Rules tab.
3. Paste the web app config into `FIREBASE_CONFIG` near the top of the second script in `index.html`. Keep `MANAGER_EMAILS` the same as the list in the rules.
4. On each store computer, open the page and pick the store. A link like `?store=usq` picks it automatically.
