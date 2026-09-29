# ACN-AMA host-controlled quiz setup

## Files
- `index.html`: participant page
- `host.html`: private host console
- `firestore.rules`: Firestore access rules

## Firebase
1. Create/register a Firebase Web app.
2. Enable Authentication > Anonymous sign-in.
3. Create Cloud Firestore.
4. Paste `firestore.rules` into Firestore > Rules and publish.
5. Copy the Firebase web configuration into BOTH HTML files, replacing all `YOUR_...` placeholders.

## GitHub Pages
Upload both HTML files to the repository root. The host opens `/host.html`; participants open the normal Pages URL ending at `/` or `/index.html`.

## Run the quiz
1. Host creates a unique non-confidential Game ID.
2. Share that Game ID and the participant URL in Teams.
3. Up to 50 participants join the lobby.
4. Host pushes a question, waits 30 seconds, reveals the answer, shows the leaderboard, then pushes the next question.
5. Host ends the quiz after question 11.

## Important security note
The host is protected by the anonymous Firebase user ID that created the room, which Firestore rules enforce. Do not clear browser site data or switch browser/profile during the game, because that creates a new anonymous identity. Client-side scoring is appropriate for a friendly team activity but is not tamper-proof. A tamper-resistant competition requires server-side answer validation, such as a Cloud Function.
