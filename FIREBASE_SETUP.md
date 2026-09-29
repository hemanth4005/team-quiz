# Firebase setup for Ops Arena

1. Create a Firebase project in the Firebase Console.
2. Register a Web app under Project settings.
3. Copy the Firebase configuration values into `firebaseConfig` in `index.html`.
4. In Authentication, enable the Anonymous sign-in provider.
5. Create a Cloud Firestore database.
6. Open Firestore Database > Rules, replace the rules with `firestore.rules`, and publish.
7. Commit `index.html` to the root of your GitHub Pages repository.
8. Open the GitHub Pages URL. Confirm the page says the shared leaderboard is connected.
9. Send the same Game ID to all participants. Use a new non-confidential Game ID each month.

Security note: This is a lightweight team game. Browser-side scoring can be manipulated by a technically skilled participant. For tamper-resistant scoring, move score calculation to a trusted backend such as a Cloud Function.
