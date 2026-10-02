APRM Lucky Draw Cloud COMPLETE v8

UPLOAD THESE TO THE ROOT OF THE EXISTING GITHUB PAGES REPOSITORY:
- index.html
- draw2.html
- draw3.html
- operator-7x29.html
- aprm-logo.png

URLs:
Main:     https://kouku0508.github.io/aprm-lucky-draw/
2-digit:  https://kouku0508.github.io/aprm-lucky-draw/draw2.html
3-digit:  https://kouku0508.github.io/aprm-lucky-draw/draw3.html
Settings: https://kouku0508.github.io/aprm-lucky-draw/operator-7x29.html
PIN: 0508

Cloud behavior:
- Participants, winner history and weighting are stored in Firestore aprm/state.
- Both draw modes use the same winner history, preventing a winner from winning again in the other mode.
- Winner reservation is performed inside a Firestore transaction, preventing two draw devices from reserving the same winner concurrently.
- Bottom-right APRM is shown only after a server-backed Firestore snapshot containing configVersion is received.
- Settings SAVE writes a new configVersion. Draw pages receive the new version in real time.
- If cloud data cannot be verified, APRM disappears and START DRAW is disabled.

IMPORTANT SECURITY NOTE:
PIN 0508 is a client-side convenience lock. Current Firestore rules require Firebase authentication but do not make the PIN a server-side administrator credential. Do not publish the operator URL broadly.
