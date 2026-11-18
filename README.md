# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/FajarRizikAinulyakin/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/FajarRizikAinulyakin/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

Entry for the make.fun bounty **tiny-chess-01**: the strongest chess
engine in 4,096 bytes of Python. `main.py` is the whole engine — no
other file is read at runtime.

## Engine

- 0x88 board, alpha-beta + quiescence (captures, promotions, check
  evasions), Zobrist transposition table, killer moves, repetition-aware
  search (game history + search path score 0, as the house engine does),
  iterative deepening to a fixed 60,000-node budget per move.
- Evaluation: material + formula piece-square terms (the house
  eval's shape), bishop pair, king middlegame/endgame blend.
- Deterministic: fixed node budget, never a clock, no randomness.
  Python 3.13, standard library only.

## Practice results (kit gauntlet, 6 games per trial, 60k nodes/move)

| trial | Elo | W/D/L |
|---|---|---|
| 0 | 1,545 | 4/1/1 |
| 1 | 1,279 | 2/2/2 |
| 2 | 1,099 | 1/2/3 |
| mean | 1,308 | — |

Sunfish 4K baseline mean: 1,365. Final floor: 1,154.
