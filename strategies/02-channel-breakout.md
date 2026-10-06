# S02 — Channel breakout, version 1

Hypothesis: closing above recent highs may indicate a sustained expansion. This tests a different trend signal from S01 but shares exposure to trend regimes.

- Enter long when today's close exceeds the highest high of the preceding 20 completed sessions and close exceeds SMA200. Exclude today from the breakout channel.
- Execute at the following open, one position per stock.
- Exit when close is below the lowest low of the preceding 10 completed sessions, close falls below SMA200, the initial two-ATR stop triggers, or 60 sessions have elapsed.
- No entry when shared gates fail. Do not count current-day high in the entry threshold or read tomorrow's open when deciding whether to enter.

Failure mode: false breakouts, expensive gaps and choppy periods. Status: unproven. Do not interpret agreement with S01 as two independent confirmations of an edge.
