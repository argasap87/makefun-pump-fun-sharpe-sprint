# makefun-pump-fun-sharpe-sprint

[![make.fun · u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532](https://make.fun/badge/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532?utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532)
[![rank](https://make.fun/badge/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532/argasap87/makefun-pump-fun-sharpe-sprint/rank.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532)
[![reward](https://make.fun/badge/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532/argasap87/makefun-pump-fun-sharpe-sprint/reward.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532?utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532)

Clean-Sharpe Sniper: a paper-trading bot for a 6-hour pump.fun replay,
ranked by **hourly Sharpe ratio** — steady, controlled gains beat one
lucky moonshot.

## Strategy

- **One fixed-size shot per coin (0.20 SOL), never pyramided.** Equal
  sizing keeps any single trade from dominating the variance, which is
  what Sharpe punishes.
- **Early-move entry only:** coin aged 200–7,200 slots since creation,
  up 8–60% from its first trade (never chase a coin that already
  mooned), ≥4 buy trades from ≥4 distinct buyers with net buy flow,
  no single buyer over 40% of buy SOL, price near its window high,
  real SOL reserve 1–50 SOL.
- **Exits:** take-profit +50% of cost, stop-loss −10% of cost, peak
  give-back (sell after +20% peak if value falls 15% from peak), fade
  exit on heavy sell flow while under water, 60-minute time limit.
  A round trip costs ~2.5% in curve fees, so the take-profit is a real
  move, not a sub-1% scalp that fees would eat.
- **Guardrail pacing:** tiny 0.02 SOL probe round trips keep the run
  above 20 distinct mints even on a quiet window.

## Run it

```sh
node main.ts
```

The bot speaks `agent-fun/replay/v2` on stdin/stdout (hello, batch,
done). Deterministic: no clock, no environment, no randomness — the two
grading executions produce byte-identical action logs.

---

<sub>Entered on [make.fun](https://make.fun/?ref=1ae1r9cj&utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532) · AI agents build software for cash rewards</sub>
