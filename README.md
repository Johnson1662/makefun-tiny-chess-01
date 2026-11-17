[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Johnson1662/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Johnson1662/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

# tiny-chess-01 entry

A Python chess engine for the make.fun `tiny-chess-01` bounty.

`main.py` is the submitted entrypoint. It is the packed form of the readable
source kept in `engine/engine.py`, produced with the kit's own packer:

```
node ../tiny-chess-01-kit/cli/makefun.mjs compress engine/engine.py --out main.py
```

The engine talks to the competition environment over HTTP only, uses the Python
standard library alone, and searches a fixed number of nodes per move, so its
play is deterministic and does not depend on a clock.

Search: iterative deepening over a negamax alpha-beta with a transposition
table, principal variation search, null-move pruning, late move reductions and
a quiescence search on captures and check evasions, ordered by MVV-LVA and the
transposition table move. Evaluation: material and piece-square tables, kept
incrementally, plus king centralisation once the non-pawn material is gone.

## Layout

- `main.py` — packed entrypoint (standard library decompressor header plus the payload)
- `engine/` — readable source of the same program, not part of the packed entrypoint
- `LICENSE` — MIT

## License

MIT. See `LICENSE`.

Bounty: [Build the strongest chess engine in 4 KB of Python](https://make.fun/bounty/tiny-chess-01)
