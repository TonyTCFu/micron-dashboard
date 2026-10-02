# MEMORY.md

Lam Research Corporation (NASDAQ: LRCX) tracking dashboard. Static single page
served by GitHub Pages. This repo is independent of `tempus-dashboard`,
`spacex-dashboard`, `nvda-dashboard`, and `micron-dashboard`; keep them separate
(own quote.json, own workflow, own public link).

## Deployment
- Public link: https://tonytcfu.github.io/lam-research-dashboard/
- Source: `index.html` at the `main` branch root, generated from the
  `lam-research-dashboard` web artifact (re-export on data updates; do not hand-edit).
- GitHub Pages setting: Deploy from a branch / main / /(root).

## Quote snapshot
- `quote.json` at repo root; refreshed by `.github/workflows/quote.yml`
  (cron `*/15 13-21 * * 1-5` UTC, Mon-Fri, plus manual dispatch).
- Source: Nasdaq official API (`api.nasdaq.com/api/quote/LRCX/info`), real-time.
- Page fallback chain: quote.json -> Nasdaq direct -> Yahoo Finance -> Stooq (lrcx.us).
- Format: {"symbol":"LRCX","price":..,"netChange":..,"pctChange":..,"prevClose":..,
  "quoteTime":"YYYY-MM-DD HH:MM","status":"intraday|postmarket|close","source":"Nasdaq"}.

## Data baseline
- Price/financials/short/analyst snapshot: 2026-10-01 close ($340.10, +3.53%,
  sympathy rally on Micron's blowout FQ4).
- Q4 FY2026 (2026-07-29): revenue $6.72B (+30% YoY), non-GAAP EPS $1.82
  (beat $1.69), non-GAAP GM 52.0% (20-yr high); Q1 FY2027 guide: revenue
  $8.10B ±$400M, non-GAAP EPS $2.15 ±$0.15. Dividend raised 27% to $0.33/qtr
  (payable 10/14).
- Short interest (FINRA 2026-09-15): 26.08M shares, 2.09% of float, 3.1 days
  to cover (down from 27.75M prior).
- Analyst consensus: 32 firms, Moderate Buy, avg target ~$361.81 (Oct 2026);
  18-firm ladder on page (BofA $480 at top).
- Options (2026-10-01): dealer GEX positive (+$70.2M FlashAlpha), call wall $340,
  put wall $280, max pain $280, P/C OI 1.15, 30d ATM IV ~53.6-62.7% (rank 62/100).
- Note: lamresearch.com/favicon.ico is an empty file; the dashboard icon uses the
  verified cropped-Favicon_512 PNG (Lam triangle logo), inlined as data URI.
