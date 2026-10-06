# S04 — Range reversion, version 1

Hypothesis: an unusually low close may revert toward the mean when the longer trend is sufficiently flat.

- Compute a 20-session mean and population standard deviation of close. Enter below mean minus twice the standard deviation, only if absolute SMA50 / SMA200 minus one is below 0.05.
- Execute at the following open, one position per stock.
- Exit when close reaches the 20-session mean, the initial two-ATR stop triggers, or ten sessions have elapsed.
- No entry when shared gates fail or standard deviation is zero. No averaging down.

Failure mode: a previously stable range turning into a persistent decline. The 5% regime threshold and two-standard-deviation band are explicitly experimental, not optimized. Status: unproven.
