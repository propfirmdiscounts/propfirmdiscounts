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

A flat JSON array — one object per firm — so dataset viewers read each firm as
a row:

```json
[
  {
    "prop_firm": "Alpha Futures",
    "code": "Tran009503",
    "discount": "15%",
    "validity": "standing",
    "last_deal_published": "2026-10-28",
    "activation_link": "https://propfirmdiscount.com/go/...",
    "archive_url": "https://propfirmdiscount.com/prop-firm/alpha-futures/",
    "trustpilot_score": 4.5,
    "trustpilot_reviews": 1200
  }
]
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
