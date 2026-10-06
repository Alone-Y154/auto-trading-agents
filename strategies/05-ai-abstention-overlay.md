# S05 — AI abstention overlay, version 1 (prospective only)

Hypothesis: an AI review may improve a quantitative strategy by abstaining on unsuitable opportunities. It must beat the same strategy without AI, after model costs, rather than claim success from persuasive explanations.

The initial AI role is deliberately bounded: the selected quantitative baseline proposes an entry; AI outputs `ALLOW`, `ABSTAIN` or `DATA_INSUFFICIENT`. Hard data and risk gates run first. AI cannot enlarge size, move a stop, bypass a gate, or veto required protective exits. This gives the intended AI decision engine a measurable first responsibility before expanding its authority.

## Packet and response

Input: decision timestamp in IST, latest completed bar timestamp, permitted price history through that time, computed signal, exposure, liquidity, volatility, and optionally source-linked news published before that timestamp. Never use current news to reconstruct historical decisions. Record retrieval time as well as publication time.

Output: action, reason codes, short rationale, missing information, model identifier, prompt version, input hash, latency and measured API cost. Self-reported confidence is not a calibrated probability. Malformed output, timeout, stale bars or missing required information means no new entry.

Start with price-only packets. Do not imply that an OHLCV API supplies news, corporate-action verification or event calendars. Add news only after a timestamped source is available.

## Evaluation

Run paired virtual portfolios: baseline alone and baseline with AI gate, using identical capital and execution. Preserve all rejected opportunities and their later outcomes. Measure net return, drawdown, exposure, skipped winners/losers, abstention rate, errors and API cost. Require at least 60 market sessions, and extend until at least 30 actual entry decisions exist; this is an operational minimum, not statistical proof.

No historical AI performance is claimed. Present-day LLMs may know outcomes from historical dates, so an ordinary retrospective prompt is not an honest AI holdout. Credentials are optional for the mathematical study and needed only when this separately logged experiment is enabled.
