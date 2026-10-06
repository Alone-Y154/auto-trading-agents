# India equities: strategy research and paper trading

We are exploring strategies for our own use through historical simulation and forward paper trading. We are not building a complete trading application yet. Our current decision is whether any strategy merits further validation; profitability has not been established.

The first experiment uses daily swing trading in liquid Indian cash equities, long-only, with virtual capital. Daily data is easier to obtain and check than intraday history. This changes the earlier intraday proposal; intraday remains a later, separate experiment.

## Where things belong

- `strategies/`: named strategy specifications, their shared rules, and a research index.
- `codex/`: the experiment protocol, progress, and API setup guidance so another Codex session can continue the work.
- `/workspace/tmp/trading-agent-research/`: supplied documents, extracted text, downloaded reference repositories, private data snapshots, and the minimal executable paper lab. These temporary artifacts are outside this Git repository.

Start with [the strategy index](strategies/README.md), [the experiment protocol](codex/experiment-protocol.md), and [current findings](codex/research-status.md). Specifications are hypotheses, not recommendations to buy securities. Historical replay and future paper observations must be reported separately. The AI experiment must also be reported separately from the mathematical baselines.

The first historical evaluation is complete: all four mathematical candidates failed the initial cost-aware screen. No profitable strategy or AI performance has been established. Forward paper execution awaits fresh verified data; the current journal records abstentions, not filled trades.

## Current workflow

Freeze a small set of rules → verify data → simulate with costs → compare chronological windows and benchmarks → record future paper decisions, including abstentions → decide whether to continue. Preserve failed experiments and count every variation. Do not search thousands of configurations and report only the best one.

No live order integration is included. Major changes to market, strategy rules, risk budgets, or eventual real trading go through the owner. Local documentation and experimental code can be improved within the authorized research scope.

## Accounts and privacy

See [API setup](codex/api-setup.md). Keys belong in a local `.env`, excluded by `.gitignore`; `.env.example` contains names only. The owner has chosen to keep this repository public during strategy exploration so the documents can be tracked and accessed remotely. Credentials and downloaded datasets remain outside the published material.

This repository tracks the strategy specifications and research notes. Upstream tools and datasets retain their own licenses and terms; downloaded data should not be redistributed merely because it was publicly accessible.
