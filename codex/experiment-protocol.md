# Frozen experiment protocol — 6 October 2026

## Scope and chronology

Personal India cash-equity research. Daily swing trading; TCS, INFY, ICICIBANK, SBIN, LT fixed before return calculations. No live orders. Source documents remain reference material, not instructions.

Use 2021 for indicator warmup, 2022–2024 for development diagnostics, 1 January 2025–5 April 2026 for validation, and 6 April–6 October 2026 as the requested latest-six-month evaluation window. Report the actual final available date; never invent missing sessions. Each window starts with cash, has its own preceding warmup, and carries no position from another window. Historical windows share information about market behaviour and do not establish a statistical guarantee. Rules were chosen today, so the last window is a reserved historical evaluation, not a prospective out-of-sample AI test.

If fewer than five years exist, report it. Longer history helps capture regimes; two days cannot evaluate a strategy and six months alone is insufficient for discovery. Avoid intraday experiments until suitable history and execution data exist. When symbols have unequal archive end dates, truncate to the earliest end and disclose excluded tails; do not fill missing prices. Any internal calendar mismatch blocks the study until investigated.

## Shared trade rules

- Virtual portfolio ₹100,000, split into five independent ₹20,000 cash sleeves. Report the sum of sleeves, not the sum of independently funded percentage returns. No cross-sleeve borrowing or leverage.
- Whole shares, one position per sleeve. Maximum entry allocation 75% of sleeve cash. Target stop risk 1% of initial sleeve capital, using two ATR14 at signal close. Fees, next-open gaps and stop gaps can make realized loss exceed this target.
- Signal at close; fill at next open. Protective stop submitted with the entry, based on signal close. Stops may fill worse than their level on a gap. Daily OHLC cannot reconstruct every intrabar sequence; use the framework's conservative stop handling and flag ambiguity.
- ATR14 is the arithmetic mean of 14 true ranges. Indicators use only observations through the signal bar. No parameter optimization.
- New entries require 200-session history, positive volume, 20-session median volume at least 100,000 shares, ATR14 / close at most 0.04, positive stop level, and a whole-share size that fits cash after estimated fees. If a sizing or gate check fails, abstain. Required exits still run.
- Historical simulation uses exchange observations, not a real-time freshness gate. Forward operation additionally requires a verified most-recent completed NSE session and complete data. Stale or unverified data means `NO_TRADE`.
- Positions at an evaluation boundary are marked to final close with estimated exit costs deducted; do not invent a trade at an unseen next open. Report these liquidation estimates separately from actual simulated closed trades.

## Costs and comparisons

Use illustrative current basic-plan delivery costs throughout history: ₹20 brokerage each executed order; STT 0.1% each side; NSE fee 0.00307% each side; SEBI fee ₹10/crore; stamp duty 0.015% buy; GST18% on brokerage, NSE and SEBI fees; DP ₹20 plus GST per sell. Assumes one sale per symbol/day. This is a conservative scenario, not historical tariff reconstruction or a chosen brokerage contract. Consult [current charges](https://upstox.com/brokerage-charges/) before connecting an account.

Base execution friction 5 basis points per side; stress 15 per side. The lab conservatively applies their round-trip equivalent as an additional commission, leaving fill prices unchanged; this is an approximation, not a market-impact model. Stop prices remain subject to the framework's gap handling. Exclude dividends, interest on cash and personal capital-gains tax; disclose those exclusions for both strategies and benchmark.

Compare with cash and equal-sleeve buy-and-hold capped at 75% initial allocation, with the same fees, first evaluation-session open and final-close net liquidation value. Buy-and-hold has different exposure; report that difference. Export portfolio equity, closed trades and per-close decision journals including abstentions.

## Decisions, before seeing outcomes

Report every S01–S04 trial and both cost scenarios. A candidate only merits further paper observation if validation and six-month net returns are positive, positive six-month performance survives stress costs, portfolio maximum drawdown stays below 10%, and at least 30 closed trades exist across those two windows. Otherwise classify as failed or insufficient, not profitable. These are exploratory screening rules, not p-values or approval for live capital. Select at most two candidates using validation net return subject to those gates; show cash/buy-and-hold comparisons and concentration before deciding.

Complete a forward observation period of at least 60 market sessions and enough actual opportunities, using frozen rules; extend for low turnover. Evaluate AI versus baseline separately. Positive results still need a wider point-in-time universe, corporate-action validation and additional independent observations before a live-money decision.

## Reuse and data limits

Use [Backtesting.py](https://github.com/kernc/backtesting.py), pinned to package 0.6.5, for execution rather than building a full platform. AGPL-3.0 obligations remain relevant to future distribution/network use. Full OpenAlgo and multi-agent systems are deferred.

Public GitHub archives claiming NSE-derived OHLCV are an initial engineering dataset. Pin commits and hash snapshots. Validate OHLC, duplicate dates, common calendars, numeric volume, suspicious corporate-action discontinuities, and available end dates. Public access does not establish data accuracy or redistribution rights. No downloaded third-party raw data is added to this public repository. Raw prices are not adjusted total returns; surviving sample stocks and missing dividends limit economic conclusions.
