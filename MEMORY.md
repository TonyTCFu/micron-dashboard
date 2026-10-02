# MEMORY.md

Micron Technology (NASDAQ: MU) tracking dashboard. Static single page served by
GitHub Pages. This repo is independent of `tempus-dashboard`, `spacex-dashboard`,
`nvda-dashboard`, and `lam-research-dashboard`; keep them separate (own
quote.json, own workflow, own public link).

## Deployment
- Public link: https://tonytcfu.github.io/micron-dashboard/
- Source: `index.html` at the `main` branch root, generated from the
  `micron-dashboard` web artifact (re-export on data updates; do not hand-edit).
- GitHub Pages setting: Deploy from a branch / main / /(root).

## Quote snapshot
- `quote.json` at repo root; refreshed by `.github/workflows/quote.yml`
  (cron `*/15 13-21 * * 1-5` UTC, Mon-Fri, plus manual dispatch).
- Source: Nasdaq official API (`api.nasdaq.com/api/quote/MU/info`), real-time.
- Page fallback chain: quote.json -> Nasdaq direct -> Yahoo Finance -> Stooq (mu.us).
- Format: {"symbol":"MU","price":..,"netChange":..,"pctChange":..,"prevClose":..,
  "quoteTime":"YYYY-MM-DD HH:MM","status":"intraday|postmarket|close","source":"Nasdaq"}.

## Data baseline
- Price/financials/short/analyst snapshot: 2026-10-01 close ($1,097.39, +3.03%,
  first trading day after FQ4 2026 earnings beat).
- FQ4 2026 (2026-09-30): revenue $54.23B (+379% YoY), adj. EPS $33.42,
  adj. GM 87.0%; DRAM $39.77B (73%), NAND $14.10B (26%); Q1 FY2027 guide:
  revenue $60-63B, adj. EPS $37.15-39.15. Dividend $0.15/qtr (ex-div 10/14).
- Short interest (FINRA 2026-09-15): 27.63M shares, 2.45% of float, ~1.1 days
  to cover (declining from 29.71M prior).
- Analyst consensus: ~40-49 firms, avg target ~$1,348-1,564 (Oct 2026);
  21-firm ladder on page (Melius $2,200 at top; Morningstar 2-star $850 fair value noted).
- Options (2026-10-01): dealer GEX positive (+$1.0B FlashAlpha), call wall $1,100,
  put wall $1,000, max pain $840, P/C OI 1.01, 30d ATM IV 54.1% (rank 2/100).
