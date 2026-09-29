# Card Cashback Mobile v5.5 - Single User

Implemented five production fixes:
1. Parser fields below 70% confidence require explicit field-level manual confirmation.
2. Foreign transactions are recorded as Pending FX; user must enter final issuer FX rate within 7 calendar days. Pending transactions do not consume cashback cap.
3. MCC lists validate each value as four digits or `*`.
4. Numeric validation covers fee/rate 0-100, cap >= 0, reset day 1-28, and final FX > 0.
5. User-visible transaction/card/rule fields are escaped before HTML rendering.

Deleted transactions are hidden from History. Merchant cache keys now strip Vietnamese diacritics and normalize punctuation/spacing.
