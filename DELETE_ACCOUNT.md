# Björkgatan — Delete your account

**Last updated:** 18 May 2026

This page explains how to permanently delete your Björkgatan account and all the data attached to it.

## Who this applies to

If you have created an account in **Björkgatan** (the Swedish-learning life-sim RPG developed by Kn0tas / Nostalgicore), you can ask us to delete your account and all associated data at any time. There is no charge.

## How to request deletion

Email **bjorkgatan.info@gmail.com** **from the email address you used to sign up**, with:

- Subject: `Delete my Björkgatan account`
- Body: optionally include the date you created the account, to help us confirm the right one.

We need the email request to come from the address on the account so we can verify the request is yours. If you no longer have access to that email, write from any address and include enough details (approximate signup date, character name) for us to identify the account.

## What gets deleted

When we process the request, we delete:

- Your **Firebase Authentication record** — your email address and password hash are removed.
- All of your **character save documents** in Cloud Firestore at `users/{your-user-id}/characters/*` — including character name, partner name, kid name (if any), inventory, vocabulary progress, game state, and any other in-game data.
- Your **leaderboard entry** at `leaderboards/global/entries/{your-id}` — so you no longer appear on the public leaderboard.

After deletion, nothing about you remains in the production database. The deletion is **irreversible** — we cannot restore the account afterward.

## What is retained

Nothing. We do not keep backups, anonymized profiles, analytics records, or any other trace of your account once the deletion is processed.

If we are required by law to retain certain data (for example, abuse-prevention records in the event of a serious policy violation), we will tell you what is retained and for how long.

## Timeline

We aim to process deletion requests within **7 days**. The GDPR maximum is 30 days, which we will not exceed. If you have not heard back within 7 days, please resend the email or check your spam folder for our reply.

## Partial deletion (delete one character without closing the account)

You can also delete a single character from inside the game without closing your account: open the game, sign in, and use the **delete character** option in the character selection screen. This removes only that character's save and leaderboard entry. Your account itself, and any other characters on it, remain intact.

## Privacy

For the broader privacy policy, see https://kn0tas.github.io/bjorkgatan-site/PRIVACY_POLICY

## Contact

**bjorkgatan.info@gmail.com**
