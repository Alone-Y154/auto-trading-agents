# S03 — Trend pullback, version 1

Hypothesis: a brief oversold move during an established uptrend might rebound. The short horizon makes fees and overnight risk especially important.

- Compute two-session RSI using Wilder-style exponentially smoothed gains and losses with alpha 1/2; flat prices give RSI50, rising-only prices RSI100.
- Enter when close exceeds SMA200, SMA50 exceeds SMA200, and RSI2 is below 10.
- Execute at the next open, one position per stock.
- Exit when RSI2 exceeds 60, close falls below SMA200, the initial two-ATR stop triggers, or five sessions have elapsed.
- No entry when shared gates fail. A falling price is not by itself a buying signal.

Failure mode: pullback becoming a larger decline, and small gross gains erased by delivery charges. Our RSI thresholds are experimental defaults, not findings from a paper. Status: unproven.
