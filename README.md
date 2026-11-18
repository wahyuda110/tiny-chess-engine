# tiny-chess-engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/wahyuda110/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/wahyuda110/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4 KB of Python: alpha-beta search with quiescence, a transposition table, killer moves and history ordering, and material plus piece-square evaluation. It plays the make.fun tiny-chess-01 gauntlet through the env at `MAKEFUN_ENV_URL`, searching to a fixed node budget so every game replays move for move.

## Practice results

Local practice trials (6 games each, Elo by anchor-MLE, floor 1,154):

- Trial 0: 3W 0D 3L — Elo 1,279
- Trial 1: 3W 1D 2L — Elo 1,364
- Mean Elo **1,322** — clears the floor by 168, but 43 below the sunfish baseline mean of 1,365, so a paid place is unlikely; it is a legitimate contender entry.

The node budget is 60,000/move: the 90,000-node variant measured stronger (mean Elo 1,396) but its mean think of 4.57 s/move runs past the 1,800 s trial wall, which scores 0, so the safer 60,000 was shipped. Perft passes on 5 standard positions, and the engine is deterministic across fresh processes.
