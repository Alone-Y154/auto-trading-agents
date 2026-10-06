# API handoff for the paper lab

## Recommended market-data provider

Start with **Upstox** for this India-equity daily paper study: documented historical-candle and quote APIs plus a simple manual access-token path for a personal utility. Confirm account eligibility, current historical-data access, limits and charges before opening or paying for anything. If you already use Zerodha, Kite Connect is a reasonable alternative; switching broker solely for this lab may be unnecessary.

The minimum dataset is daily OHLCV from January 2021 onward for our five symbols, reliable recent completed-session bars, stable instrument identifiers, and a way to check splits/bonuses. Corporate actions and news may require separate sources; candle availability does not imply adjustment or include dividends.

Official references: [Upstox authentication](https://upstox.com/developer/api-documentation/authentication/), [historical data V3](https://upstox.com/developer/api-documentation/v3/get-historical-candle-data/), [Kite Connect](https://zerodha.com/products/api/).

As checked on 6 October 2026, Upstox documents daily candles from January 2000 with up to a decade per request (actual instrument coverage varies). Kite Connect lists its live/historical-data tier at ₹500/month; its free personal tier excludes that data. Confirm Upstox's current account/data pricing directly rather than assuming all endpoints are free.

## How to provide credentials

1. Tell Codex the provider name and available data entitlement, without secrets.
2. Generate a data-access token using the provider's own login/dashboard. Do not give Codex a password, OTP or recovery code.
3. Copy `.env.example` to `.env` in this repository and fill `UPSTOX_ACCESS_TOKEN` locally, or configure it through the managed environment's secret settings. `.env` is ignored. Where the provider offers scope restrictions, select market-data/read-only access; a token may otherwise be capable of more than reading.
4. Tell Codex **“the market-data secret is configured”**, not its value. We check presence without printing it. Only data GET calls belong in this lab; no order-placement integration is needed.

This managed workspace currently permits GitHub/package hosts but blocks direct NSE, Yahoo and broker endpoints. A key will not fix that network restriction. Configure allowed network destinations in the environment settings, or download daily CSVs locally and supply those non-secret files. Do not bypass the managed proxy. Until access works, we can use pinned public archives for historical engineering checks, and fresh verified CSVs for manual paper sessions.

## OpenAI

An Android APK is unnecessary. If you meant **API key**, create a dedicated OpenAI project, set a small budget alert and use restricted key permissions where available. Put the key in local `OPENAI_API_KEY` or managed secrets; optionally set `OPENAI_PROJECT_ID`. Budget alerts are not a hard spending cap; the paper runner also needs its own call limits before AI is enabled.

Leave `ENABLE_AI=false` during quantitative testing. The AI overlay specification is saved, but the API caller has not yet been enabled. We will choose a model and record measured usage when the paired forward experiment starts. No OpenAI key is required for the present historical lab.
