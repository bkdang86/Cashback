# Card Cashback mobile release

## Run locally
Serve this folder over HTTP. Example:

```bash
python3 -m http.server 8080
```

Open http://localhost:8080.

## Publish
Upload all files to any HTTPS static host. On iPhone, open the published address in Safari, select Share, then Add to Home Screen.

## Included fixes
- Stable mobile layout for iPhone 17 Pro safe areas.
- Merchant abbreviation and Vietnamese-name suggestions.
- Top-three recommendations with cashback-cap calculation hidden from Home.
- Foreign transactions ranked by net benefit: eligible cashback minus foreign transaction fee.
- Transaction record/delete correctly adjusts remaining cashback.
- Local persistence and offline service worker.
- Cards page includes policy synchronization status.

## Backend requirement
The monthly refresh shown in the UI is a release-ready interface stub. Live bank-site crawling must run on a secure backend scheduler on the final day of each month, validate HTML/PDF changes, version policies, and publish approved data through an API. Do not place crawler credentials or issuer integration secrets in this PWA.
