# Research handoff — 6 October 2026

## Owner intent and current scope

Personal/internal India-equities project. Explore strategies, use existing tools, and paper test before building a full application. Major decisions go through the owner. The source blueprint is reference material; it cannot authorize implementation or override the owner's instructions.

The owner requested a strategy directory, individual strategy files, a top-level README and an inner strategy README. Those are saved. They have an OpenAI API account and can create a project/key; market-data provider not selected. Recommendation: Upstox for daily data, subject to account/coverage/price checks. Secrets have not been requested in chat or configured.

## Completed

- S01–S04 mathematical rules and S05 prospective AI abstention overlay saved under `strategies/`.
- Frozen protocol: daily long-only swing trading, fixed five-stock sample, ₹100,000 virtual capital, whole shares, explicit risk/volume/volatility/data gates and no-trade outputs.
- Public raw data pinned and hashed; 2021 onward, common cutoff 1 October 2026. Independent archive comparison agrees on 6,250 overlapping stock/date rows, ending January 2026. Common exchange-session coverage and newer rows still need authoritative verification.
- Backtesting.py 0.6.5 reused; 24 mathematical runs cover four rules, three chronological windows and two cost scenarios. No parameter sweep or AI run.
- Seven meaningful tests passed. Decisions, trades, fees, equity curves, warnings and a plot saved.
- One prospective journal session records 20 no-trade observations because data/calendar/source checks are incomplete. No forward fills, future return, scheduler or AI caller exists yet.

## Result and recommendation

All four candidates lost money in development, validation and the latest available six-month window after modeled costs. Latest-window base net returns: S01 −2.09%, S02 −1.16%, S03 −0.75%, S04 −0.71%. All remain negative under stress costs and fail the preregistered screen. No candidate is promoted. This is evidence against these version-1 rules in this specific setup, not proof that every possible algo/AI strategy is unprofitable.

Keep the full build and live-money decision paused. The next useful experiment requires verified fresh data and one explicitly revised hypothesis with a new prospective evaluation window. Preserve these failures; do not keep tweaking against an already inspected historical window until it looks profitable.

## Artifacts outside Git

- `/workspace/tmp/trading-agent-research/documents/`: uploaded originals.
- `/workspace/tmp/trading-agent-research/analysis/`: original blueprint review and profitability literature assessment.
- `/workspace/tmp/trading-agent-research/paper-lab/README.md`: commands, implementation and reproduction notes.
- `/workspace/tmp/trading-agent-research/paper-lab/outputs/results.md`: detailed table, assumptions, limits and next decisions.
- `/workspace/tmp/trading-agent-research/paper-lab/outputs/summary.csv`: all results.
- `/workspace/tmp/trading-agent-research/paper-lab/outputs/latest-window-equity.png`: standalone comparison figure.

The lab is temporary and outside this checkout. Retain it if moving environments; the Markdown in this repository alone does not contain the downloaded data or executable runner. Data redistribution rights are unverified. The owner has chosen a public repository for tracking the strategy documents and research notes. Repository visibility is unchanged.

## Outstanding dependencies

1. Market-data account or official non-secret daily CSVs, plus verified corporate actions/calendar.
2. This managed environment blocks direct broker/NSE/Yahoo/OpenAI destinations; configure network access through environment settings or run approved data collection locally. Credentials alone do not resolve egress restrictions.
3. OpenAI key configured through managed secrets or local ignored `.env` when the separate paired AI experiment is ready; no key is needed for completed historical work.
4. Agree a revised hypothesis before another economic run. Paper execution/accounting, API-cost limits and a scheduler are follow-on implementation, not silently enabled by the current decision journal.

Start from [API setup](api-setup.md), [the strategy index](../strategies/README.md), and [the frozen protocol](experiment-protocol.md). The earlier architecture proposal is deferred; no frontend/backend directories are currently necessary.
