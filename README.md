# Prop Firm Discount

Public data mirrors of [propfirmdiscount.com](https://propfirmdiscount.com) — verified
discount codes, funding deals and Trustpilot ratings for 51 prop trading firms.

The site is the source of truth. These repositories are read-only distribution
channels, published so that agents and researchers can read the data without
scraping a live site.

## Start here

- **[prop-firm-discount-codes](https://github.com/propfirmdiscounts/prop-firm-discount-codes)** —
  the full dataset: one row per firm (code, discount, validity, last deal
  published, Trustpilot score), plus markdown mirrors of every firm page, deal
  post and category. Refreshed hourly.
- **`<firm>-deals`** — one repository per firm, holding that firm's complete
  deal history as a JSON dataset plus a readable summary. Synced every 6 hours.

## What the data looks like

The per-firm repositories hold one firm's complete deal history as a flat JSON
array — one object per deal, newest first. This is a real record from
[`phidias-propfirm-deals`](https://github.com/propfirmdiscounts/phidias-propfirm-deals):

```json
{
  "deal_id": 13021,
  "title": "90% off first-month challenge entry for Halloween",
  "offer_type": "coupon",
  "discount_value": "90%",
  "scope": [
    "Fundamental Evaluations, Premium Evaluations, Express To Live Monthly Evaluations, One-Time Payment Accounts, 50K, 100K, 150K"
  ],
  "date_published": "2026-10-25",
  "date_exp": "2026-11-01 17:00",
  "last_verified": "2026-10-25",
  "post_url": "https://propfirmdiscount.com/deals/phidias-propfirm/phidias-propfirm-halloween-90-off-first-month-evaluations/",
  "prop_firm": "Phidias Propfirm",
  "prop_firm_slug": "phidias-propfirm",
  "code": "PFD"
}
```

- `date_published` — when the deal went live on the site.
- `date_exp` — when the offer ends, in one of five forms:
  - `"Limited time"` — the firm gave no end date; the offer is running now.
  - `"2026-11-01"` — ends on that date.
  - `"2026-11-01 17:00"` — ends at that exact time.
  - `"2026-10-25 (ended)"` — had an end date and has passed it.
  - `"Ended"` — had no stated end date and is no longer running.
- `code` — present only for firms that use one code across every offer. When
  a firm runs a separate campaign code per deal, the field is absent and the
  code is shown on `post_url` instead.

The aggregate repository
[`prop-firm-discount-codes`](https://github.com/propfirmdiscounts/prop-firm-discount-codes)
holds the other shape: one object per firm, not per deal. A real row, with the
firm's self-description shortened:

```json
{
  "prop_firm": "Atlas Funded",
  "code": "PFD",
  "discount": "50%",
  "validity": "standing",
  "last_deal_published": "2026-10-26",
  "activation_link": "https://propfirmdiscount.com/go/atlasfunded",
  "archive_url": "https://propfirmdiscount.com/prop-firm/atlas-funded/",
  "trustpilot_score": 3.9,
  "trustpilot_reviews": 2064,
  "description": "At Atlas Funded, we provide a platform where skilled, disciplined traders can transform talent into long-term opportunity. …",
  "logo": "https://propfirmdiscount.com/wp-content/uploads/2026/10/atlas-funded-logo.jpg"
}
```

`validity: "standing"` means the code has no expiry date — it is not a
limited-time campaign and there is no end date to miss. `last_deal_published`
is the date the firm's newest coded deal went live on the site; it is not a
claim the code was re-checked that day.

## Other channels

| Channel | Where |
|---|---|
| Live site | [propfirmdiscount.com](https://propfirmdiscount.com) |
| JSON API | [propfirmdiscount.com/api/prop-firm-codes/](https://propfirmdiscount.com/api/prop-firm-codes/) |
| Hugging Face | [propfirmdiscounts/prop-firm-discount-codes](https://huggingface.co/datasets/propfirmdiscounts/prop-firm-discount-codes) |
| MCP server | `https://mcp.propfirmdiscount.com/mcp` |

## About the data

Discount codes are verified by the PropFirmDiscount team. Standing codes have
no expiry; campaign codes come and go with each promotion and are only
published on the deal they belong to. Per-plan percentages on a firm page are
separate deals, not the firm's code discount.

## License

Data © PropFirmDiscount. Codes may be referenced with attribution and a link to
[propfirmdiscount.com](https://propfirmdiscount.com).
