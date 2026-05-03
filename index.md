# TCGScan — Privacy Policy

*Last updated: 2026-05-02*

This is the canonical text for TCGScan's privacy policy. It satisfies Google Play's requirement for a privacy policy URL on apps that request the `CAMERA` permission. A render-hosted version of this text must be reachable at a stable public URL (suggested: `https://longstreetcomics.github.io/tcgscan-privacy/` — see `deployment` section below) and that URL goes into Play Console → Setup → App content → Privacy policy.

> **Status:** placeholder. The substantive policy text below is accurate for the current TCGScan implementation (no analytics, no third-party trackers, no ad networks). Update before launch (M6) if any of those change.

---

## What TCGScan does

TCGScan is a trading-card-game scanning app for Magic: The Gathering and Pokémon TCG. It uses the device camera to capture images of trading cards and identify them via a third-party AI service.

## What data we collect

### Information you provide
- **Account information** — email address (used for Supabase authentication only)
- **Card collection data** — the cards you scan and add to your collections
- **Optional notes** — any text you attach to a card (acquisition price, condition notes)

### Automatic collection
- **Captured card images** — the cropped image of each card you scan is sent to our card-identification service ([Ximilar](https://ximilar.com)) for processing
- **Identification results** — the response (card name, set, market price) is stored alongside your scan history
- **Crash and error reports** — if a crash reporter is enabled in a future release, anonymized stack traces and device model

### What we DO NOT collect
- We do **not** track your location
- We do **not** collect device contact lists
- We do **not** display ads or share data with ad networks
- We do **not** sell your data to anyone

## How we use the data

- To identify the cards you scan (sent to Ximilar for AI recognition)
- To save your collections and decks across your devices
- To show you market pricing for your cards
- To improve scan accuracy by aggregating anonymized scan-success metrics (no personal data)

## Third parties

| Service | What they receive | Why |
|---------|-------------------|-----|
| [Supabase](https://supabase.com) (Postgres + Auth + Realtime, hosted in US) | Your email, your card collections and decks, your scan history | App backend — accounts and sync |
| [Ximilar](https://ximilar.com) (image recognition) | Cropped card images you scan, anonymized | AI card identification |
| [Scryfall](https://scryfall.com) (free MTG metadata) | Card identifiers (no personal data) | Card art and metadata enrichment |
| [PokémonTCG.io](https://pokemontcg.io) (free Pokémon metadata) | Card identifiers (no personal data) | Card art and metadata enrichment |

If we add an analytics tool (PostHog, Mixpanel) or a crash reporter (Sentry, Firebase Crashlytics) in a future release, this list will be updated.

## Where the data lives

- **Server-side:** US-East-1 (Supabase managed Postgres)
- **On your device:** local Drift / SQLite cache for offline access
- We do **not** retain captured card images on our servers — they're discarded after the identification call returns

## Your rights

- **Export:** request a copy of your data via the in-app "Export collection" feature (CSV/JSON)
- **Delete:** request account deletion via the in-app "Delete account" feature, or by emailing us (see Contact below)
- **Access:** all your data is visible in the app's collection and deck screens
- **Portability:** exported data is in standard formats (CSV, JSON, MTGO/Moxfield deck text)

If you're in the EU, UK, or California, you have additional rights under GDPR / UK GDPR / CCPA. Contact us to exercise them.

## Children

TCGScan is not directed at children under 13. We do not knowingly collect data from children under 13. If you believe we have collected data from a child, contact us and we'll delete it.

## Security

All data in transit is encrypted via TLS 1.3. Supabase Row Level Security (RLS) ensures users can only read or modify their own data. Tokens are stored on-device in OS-level secure storage (iOS Keychain, Android EncryptedSharedPreferences).

## Changes to this policy

We'll update the "Last updated" date at the top of this document whenever the policy changes. For material changes, we'll notify users via in-app notification.

## Contact

- Email: robertdyche@gmail.com
- Mailing: Long Street Comics — address on request

## Jurisdiction

This policy is governed by the laws of the United States.

