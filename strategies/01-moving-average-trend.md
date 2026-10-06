# S01 — Moving-average trend, version 1

Hypothesis: upward price persistence might outweigh the losses from false starts. This is a simple baseline inspired by trend literature; the exact rule is our hypothesis.

- Daily close signals; enter long when the 20-session simple moving average exceeds the 50-session average and close exceeds the 200-session average. This is a state condition, not just a one-day crossover.
- Submit after the close for the following session's open. At most one position per stock; no shorts or pyramiding.
- Exit when SMA20 falls below SMA50, close falls below SMA200, the protective stop triggers, or 60 sessions have elapsed.
- Initial protective stop: signal close minus twice the 14-session ATR. Do not widen it. A next-open gap changes effective entry risk; sizing uses the observed signal price, not an unseen future open.
- No entry when shared data, volume, volatility or sizing checks fail. A sideways market can repeatedly stop out this strategy.

Primary comparison: net return and drawdown versus cash and equal-sleeve buy-and-hold, with lower exposure explicitly reported. Status: unproven; quantitative baseline only.
