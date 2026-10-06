# Strategy catalogue

This directory saves the actual trading hypotheses. Each file describes why we are testing it, when to enter, when to exit, and when to abstain. Shared execution and risk rules are in [the experiment protocol](../codex/experiment-protocol.md).

| ID | Strategy | Intended market behaviour | Recommendation / status |
| --- | --- | --- | --- |
| S01 | [Moving-average trend](01-moving-average-trend.md) | Sustained upward trends | Start here as an understandable baseline; unproven. |
| S02 | [Channel breakout](02-channel-breakout.md) | Expansion beyond recent highs | Test alongside S01; another trend hypothesis, not independent evidence. |
| S03 | [Trend pullback](03-trend-pullback.md) | Brief oversold moves within an uptrend | Test cautiously; frequent delivery costs may erase returns. |
| S04 | [Range reversion](04-range-reversion.md) | Prices reverting within a stable range | Test as a different hypothesis; vulnerable to regime changes. |
| S05 | [AI abstention overlay](05-ai-abstention-overlay.md) | Reject questionable rule-based opportunities | Evaluate prospectively against the same baseline in shadow mode; not historically tested. |

## Rules for changes

Version 1 was written on 6 October 2026 before evaluating strategy returns. The stock list is TCS, INFY, ICICIBANK, SBIN, LT: a small, deliberately fixed implementation sample, not a point-in-time Nifty universe. The choice still introduces survivorship and sector-selection bias.

Do not silently edit a strategy after seeing results. Create a version with the hypothesis, date, reason, and next evaluation window. Keep failed strategies and all trial counts. Four quantitative candidates plus two execution-cost scenarios are currently planned; cost scenarios are sensitivity checks, not additional independent opportunities.

No strategy has established profitable AI trading. A quantitative backtest cannot validate an AI overlay that has not actually been run. A zero-trade day is valid, and existing positions still need their prescribed exits.

## Research grounding

- [Moskowitz, Ooi and Pedersen: Time Series Momentum](https://www.aqr.com/Insights/Research/Journal-Article/Time-Series-Momentum): motivation for trend families, studied on different instruments and horizons from our rules.
- [de Groot, Huij and Zhou: Another Look at Trading Costs and Short-Term Reversal Profits](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1963131): motivation to evaluate reversal after turnover costs; not proof of S03 or S04.
- [Bailey et al.: The Probability of Backtest Overfitting](https://www.davidhbailey.com/dhbpapers/backtest-prob.pdf): why we count trials and avoid choosing from thousands of chance winners.
- [Lopez-Lira and Tang: Can ChatGPT Forecast Stock Price Movements?](https://arxiv.org/abs/2304.07619): motivation for a separately evaluated AI news experiment; timely information, costs, model versions and information leakage matter.

These are simple research-inspired hypotheses, not reproductions of the papers' strategies or returns.
