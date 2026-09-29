# Card Cashback Mobile v4

Implemented:
- No default cards.
- Initial policy retrieval in Add Card from issuer-profile data.
- No scheduled, monthly, or background policy update.
- Existing cards can be edited manually: statement day, reset day, foreign fee, category, MCC, cashback rate, monthly cap.
- Rules can be added or deleted.
- Home keeps cashback caps hidden while using them in calculations.
- Foreign transactions rank by net benefit after foreign fee.
- Merchant name is entered manually; no merchant suggestion or renaming.
- Transactions can be recorded and deleted, restoring cashback usage.

Production note: this PWA includes issuer-profile fixtures to demonstrate the one-time retrieval flow. Direct retrieval from arbitrary issuer websites requires a deployed backend endpoint. The mobile app intentionally contains no periodic scheduler.
