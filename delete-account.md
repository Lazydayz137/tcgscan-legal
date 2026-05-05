---
title: Delete your TCGScan account
---

# Delete your TCGScan account & data

*Last updated: 2026-05-04*

This page explains how to permanently delete your **TCGScan** account, what data is removed, and what (if anything) is retained.

If you have any trouble with the steps below, email **robertdyche@gmail.com** with the subject line **"Delete my TCGScan account"** and we'll process the deletion within 7 days.

---

## Option 1 — Delete from inside the app (recommended)

1. Open **TCGScan** on your device.
2. Sign in if you aren't already.
3. Tap the **profile / settings icon** in the top-right of any main screen.
4. Tap **Account**.
5. Tap **Delete account**.
6. Confirm by re-entering your email address when prompted.
7. Tap **Delete permanently**.

The app will sign you out immediately. Your account and all associated data are removed from our backend within minutes. There is no recovery — please export anything you want to keep first (Settings → Export collection).

## Option 2 — Email request

If you no longer have access to your device, send an email to **robertdyche@gmail.com** from the email address you used to sign up, with:

- **Subject:** Delete my TCGScan account
- **Body:** Confirm that you want your TCGScan account deleted. Include the email associated with the account.

We will:

1. Verify the request comes from the registered email address.
2. Delete the account within 7 days.
3. Reply confirming the deletion is complete.

---

## What gets deleted

When your account is deleted, the following data is **permanently removed**:

| Data | Where it lived | Status after deletion |
|---|---|---|
| Email address | Supabase `auth.users` | Deleted |
| Sign-in identifier (Apple/Google ID) | Supabase `auth.identities` | Deleted |
| Your collections (binders, decks, trade piles) | Supabase `collections` | Deleted (cascade) |
| Cards inside those collections | Supabase `collection_cards` | Deleted (cascade) |
| Your scan history | Supabase `scans` | Deleted (cascade) |
| Local cache on your device | Drift / SQLite | Deleted on app uninstall, or by tapping "Clear local cache" in Settings |

## What is retained, and for how long

| Data | Why retained | How long |
|---|---|---|
| Anonymized error / crash reports | Operational debugging — these never contain your email or card data | Up to 90 days, then auto-purged |
| Aggregated, non-personal scan-success metrics | Improving recognition accuracy across all users | Indefinitely, but cannot be linked back to you |
| Backups of the Supabase database | Disaster recovery only | Rolling 7-day window, then overwritten |

We do **not** retain:

- Any photos of your cards (these were never stored after identification)
- Any market price snapshots tied to your account
- Any payment information (TCGScan does not process payments)

After the rolling 7-day backup window expires, every trace of your account is gone from our systems.

---

## Data sent to third parties before deletion

While your account was active, TCGScan sent some data to third-party services. After deletion, the following applies:

| Third party | Data they received | Their retention policy |
|---|---|---|
| [Ximilar](https://ximilar.com) (card recognition) | Cropped card images at scan time | Per Ximilar's policy — images are discarded after recognition completes |
| [Scryfall](https://scryfall.com) | Card identifiers only — never your account info | No personal data was ever shared with Scryfall |
| [PokémonTCG.io](https://pokemontcg.io) | Card identifiers only — never your account info | No personal data was ever shared with PokémonTCG.io |

If you need to follow up with a third party directly, contact them using the links above.

---

## Contact

- **Email:** robertdyche@gmail.com
- **Subject for deletion requests:** *Delete my TCGScan account*

For everything else (privacy questions, GDPR/CCPA requests), see our [Privacy Policy](/tcgscan-legal/).
