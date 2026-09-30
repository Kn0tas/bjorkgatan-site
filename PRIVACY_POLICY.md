# Björkgatan — Privacy Policy

**Effective date:** 18 May 2026
**Last updated:** 28 September 2026

This privacy policy describes how Björkgatan ("the app", "we") collects and uses your personal information. We try to collect as little as possible, store it securely in the EU, and never share it with advertisers or analytics providers.

## 1. Who we are

Björkgatan is an independent Swedish-language learning game developed and operated by **Kn0tas (Björkgatan)**.

If you have any privacy questions, contact: **bjorkgatan.info@gmail.com**

Under the GDPR we are the **data controller** for the personal data described below.

## 2. What we collect

We collect account and game data to run the game, let you continue across devices, and understand how to improve the experience.

### Account data

When you sign up we collect:

- **Email address** — used as your login identifier and to send the password-reset email when you ask for one.
- **Password** — handled entirely by Google Firebase Authentication. We never see your password in plaintext; only a salted hash is stored.

We do **not** collect your real name, phone number, or any other identifier at signup.

### Game save data

When you play we store your save under your account. This includes:

- The character name and avatar you choose.
- The partner name and gender you choose during character creation.
- Any kid name you set during the in-game preschool flow.
- Game progress: current map, day number, time of day, money in-game, completed objectives, vocabulary you have learned, and similar fields needed to resume a game session.
- Inventory, fridge, freezer, and wardrobe contents.
- A timestamp of the last save.

This data is written to Cloud Firestore in the `users/{your-user-id}/characters/{character-id}` document, and is only readable by you (enforced by Firestore security rules).

### Leaderboard data

If you appear on the public leaderboard, the following fields are visible to other players:

- Your character name (the one you chose in-game — not your email).
- Your avatar.
- In-game money, total points, current Swedish level, and number of words learned.
- Your best Vasaloppet completion time, if any.

The character name is the only piece of leaderboard data that could plausibly be linked to a real person, and only if you chose your real name as your character name. You can change your character name at any time in-game, and you can delete your character (which removes your leaderboard entry) from the game's settings.

### Usage and diagnostic events

The app logs a small set of first-party product events under your own account, so we can tell whether the game is working and whether lessons are actually teaching Swedish:

- App opened / closed (session start and end, including session length).
- A daily objective (`uppdrag`) completed.
- An SFI lesson completed.
- A word crossing into "mastered."
- A caught app error, with a trimmed error name, message, and stack trace, so we can find and fix crashes and bugs.
- Tapping one of the app's own daily reminder notifications, including which reminder it was, so we can tell which reminders are useful.
- During the first ten minutes after account creation, a limited activity trail: screens and game maps visited, HUD buttons and panels opened, settings changed, NPC conversations and dialogue choices, selected world interactions, and shopping attempts and completions. Each action includes its time and the current guide objective so we can understand where new players explore or stop. This trail uses game identifiers, not entered text, character names, chat messages, or recordings of your screen.

The detailed first-ten-minute trail is limited to 500 records and uploaded in small batches. Pending records are temporarily stored on your device so an interrupted connection does not immediately lose them. The local buffer is cleared when you delete your account.

Each event is tagged with a random per-session identifier, your platform (iOS/Android/web), the app version, and, where relevant, your character level and in-game day. These events are written to `users/{your-user-id}/events` in Cloud Firestore, only readable by you. They are tied to your account, not to an individual character, so deleting a single character does not delete them; they are deleted automatically when you delete your account. We do not use a third-party analytics SDK, and this data is never sold, shared, or used for advertising or profiling.

### Welcome emails (currently disabled)

The app contains code to send a welcome email when you sign up. **This feature is disabled for the alpha release.** No welcome emails are sent, no email service is configured, and no email documents are queued. If we enable it in the future, we will update this policy and the email will only ever be sent to the address you signed up with.

### What we do **not** collect

- No third-party analytics SDK is bundled, and no event data is shared outside our own Firebase project (see "Usage and diagnostic events" above for the first-party events we do log).
- No advertising SDK is bundled. We do not show ads, and we do not share any data with ad networks.
- No location data is requested or collected.
- No camera, microphone, or contacts access is requested.
- No advertising identifier (IDFA / GAID) is read.
- No device fingerprinting.

## 3. Why we collect it (legal basis under GDPR)

| Data | Purpose | Legal basis (GDPR Art. 6) |
|---|---|---|
| Email + password | Let you sign in across devices and recover your account | Contract (Art. 6(1)(b)) |
| Game save data | Let you continue your game across sessions and devices | Contract (Art. 6(1)(b)) |
| Leaderboard entry | Show your progress on the public leaderboard, an opt-out feature | Legitimate interest (Art. 6(1)(f)) — you can delete your character to remove it |
| Usage and diagnostic events | Understand retention, lesson completion, and app stability so we can improve the game | Legitimate interest (Art. 6(1)(f)) — tied to your account and deleted when you delete it |

We never use any of this data for marketing, profiling, or automated decision-making.

## 4. Where it is stored

All data is stored on **Google Firebase** servers in the **europe-west1 (Belgium)** region. Data does not leave the European Union as part of normal operation.

Google acts as our **data processor** under a Data Processing Agreement (the standard Firebase DPA). You can read Google's privacy policy at https://policies.google.com/privacy.

Build artifacts (the app itself) are produced and signed by Expo's EAS Build service, which runs in the United States. EAS does not have access to your account data — only to the app's source code.

## 5. Who we share it with

We do **not** sell, rent, or share your data with third parties for marketing or any commercial purpose.

We share data only with our infrastructure providers, and only to the minimum extent needed to operate the app:

- **Google Firebase** — stores your account, your game save, your leaderboard entry, and your usage/diagnostic events.
- **Expo / EAS** — builds and signs the app and delivers over-the-air JavaScript updates. EAS does not see your account data.

We may disclose data if required by a binding court order, legal process, or to protect the safety of users or the public — but we do not anticipate this and would notify affected users where legally permitted.

## 6. How long we keep it

- **Active accounts** — until you delete your account or character from inside the app.
- **Deleted characters** — the character document is removed from Firestore immediately. The corresponding leaderboard entry is removed at the same time.
- **Usage and diagnostic events** — kept at the account level until you delete your account (deleting a single character does not remove them).
- **Auth records** — when you delete your account, your Firebase Auth record is also deleted, including the email and password hash.
- **Inactive accounts** — we may delete accounts that have not signed in for 2 years, after a 30-day notice email to the address on file.

## 7. Your rights under GDPR

If you are in the EU/EEA you have the right to:

- **Access** the personal data we hold about you.
- **Rectify** any incorrect data.
- **Erase** ("right to be forgotten") your data. The easiest way is the in-game delete-character / sign-out-and-delete-account flow. You can also email us.
- **Restrict** processing, or **object** to processing based on legitimate interest (the leaderboard, or usage and diagnostic events).
- **Port** your data to another service in a machine-readable format. Email us and we will send a JSON export of your save.
- **Withdraw consent** at any time where processing is based on consent.
- **Lodge a complaint** with your local data protection authority. In Sweden this is the Integritetsskyddsmyndigheten (IMY): https://www.imy.se.

To exercise any of these rights, email **bjorkgatan.info@gmail.com**. We will respond within 30 days.

## 8. Children

Björkgatan is intended for users aged **13 and older**.

We do not knowingly collect personal data from anyone under 13. If you believe a child under 13 has signed up, please email us and we will delete the account.

In some jurisdictions, including parts of the EU, the digital consent age is higher than 13. If you are under the age of digital consent in your country, please ask a parent or guardian to set up the account on your behalf.

## 9. Security

- All communication between the app and Firebase uses HTTPS.
- Passwords are stored only as salted hashes inside Google Firebase Auth — we cannot read them.
- Firestore security rules enforce that each user can read and write only their own save document.
- Leaderboard entries are validated by Firestore security rules to ensure each player can only write their own entry, with strict bounds on the data shape.
- The app is signed with a private keystore that we control via EAS Build.

No internet-connected system is perfectly secure, but we have taken reasonable steps to protect your data.

## 10. Changes to this policy

We may update this policy from time to time — for example if we add a new feature that processes data differently. When we do:

- We bump the "Last updated" date at the top.
- If the change is **material** (new data category, new third party, new purpose), we will also notify you in-app the next time you open the app, before you continue using it.

You can always read the current version of this policy at the URL where this page lives.

## 11. Contact

Privacy questions, data requests, or anything else:

**bjorkgatan.info@gmail.com**
