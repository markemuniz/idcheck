# TTA ID Check

A license and state ID scanner for The Travel Agency's four stores: SoHo, Union Square, Downtown Brooklyn and 5th Ave.

Plug a 2D barcode scanner that reads PDF417 into the computer, open the page, and scan the back of the ID. The page shows CLEARED, UNDER 21, EXPIRED, CHECK ID or BANNED. It reads every US state, DC, US territory and Canadian province.

## Visits and bans

Every barcode scan is saved as a visit. Managers sign in with Google to:

- **Visits**: pick a day and store to see who came in, by time, or find someone by last name. Open anyone's full visit history.
- **Ban**: from any visit, ban the person at all four stores with a reason and a note. The next time their ID is scanned anywhere, the screen shows BANNED.
- **Bans**: see who is banned, lift a ban, or add a ban by name and birth date for someone who isn't in Visits.

Bans match the ID number and also the name and birth date, so a new license number still gets caught. Store computers sign a manager out after 15 idle minutes.

## Privacy

- **Visits** (managers only): name, age, sex, height, eye color, issuing state, last 4 of the ID number, store, station, time and result. Kept until deleted.
- **Scan counts** (Reports): age, result, reason, issuing state, store, station and time. No names.
- **Never saved**: birth dates, full ID numbers and addresses. Visits and bans hold a one-way fingerprint of the ID number and of name plus birth date, so they can be matched later without storing the numbers.
- Store computers can check whether a scanned ID is banned, but can't list the ban list or read names.

New York's rule 9 NYCRR 123.10(d)(5) limits recording customer personal information without consent, beyond what is typically collected in a sale. Confirm this use with TTA compliance.

## Setup

1. Create a Firebase project. In Authentication, turn on **Anonymous** and **Google** sign-in, and add `markemuniz.github.io` under Authorized domains.
2. Create a Firestore database and paste `firestore.rules` into its Rules tab.
3. Paste the web app config into `FIREBASE_CONFIG` near the top of the second script in `index.html`. Keep `MANAGER_EMAILS` the same as the list in the rules.
4. On each store computer, open the page and pick the store. A link like `?store=usq` picks it automatically.
